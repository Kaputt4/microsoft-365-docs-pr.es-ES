---
title: Tabla CloudAppEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre eventos de servicios y aplicaciones en la nube en la tabla CloudAppEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928458"
---
# <a name="cloudappevents"></a><span data-ttu-id="df069-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="df069-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="df069-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="df069-105">**Applies to:**</span></span>
- <span data-ttu-id="df069-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df069-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="df069-107">Actualmente disponible en versión preliminar, la tabla del esquema de búsqueda avanzada contiene información sobre las actividades en diversas aplicaciones y servicios en la nube, específicamente `CloudAppEvents` Microsoft Teams y Exchange Online. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="df069-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="df069-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="df069-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="df069-109">Esta tabla se expandirá para incluir más actividades supervisadas por Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="df069-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="df069-110">Finalmente, esta tabla incluirá la actividad de archivos almacenada actualmente en la [tabla AppFileEvents.](advanced-hunting-appfileevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="df069-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="df069-111">Microsoft proporcionará instrucciones adicionales a medida que se muevan más datos a esta tabla.</span><span class="sxs-lookup"><span data-stu-id="df069-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="df069-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="df069-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="df069-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="df069-113">Column name</span></span> | <span data-ttu-id="df069-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="df069-114">Data type</span></span> | <span data-ttu-id="df069-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="df069-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="df069-116">datetime</span><span class="sxs-lookup"><span data-stu-id="df069-116">datetime</span></span> | <span data-ttu-id="df069-117">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="df069-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="df069-118">cadena</span><span class="sxs-lookup"><span data-stu-id="df069-118">string</span></span> | <span data-ttu-id="df069-119">Tipo de actividad que desencadenó el evento</span><span class="sxs-lookup"><span data-stu-id="df069-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="df069-120">string</span><span class="sxs-lookup"><span data-stu-id="df069-120">string</span></span> | <span data-ttu-id="df069-121">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="df069-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="df069-122">string</span><span class="sxs-lookup"><span data-stu-id="df069-122">string</span></span> | <span data-ttu-id="df069-123">Identificador único de la aplicación</span><span class="sxs-lookup"><span data-stu-id="df069-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="df069-124">string</span><span class="sxs-lookup"><span data-stu-id="df069-124">string</span></span> | <span data-ttu-id="df069-125">Identificador único de la cuenta en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="df069-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="df069-126">string</span><span class="sxs-lookup"><span data-stu-id="df069-126">string</span></span> | <span data-ttu-id="df069-127">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="df069-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="df069-128">Normalmente, una combinación de un nombre o nombre, una iniciación intermedia y un apellido o apellido.</span><span class="sxs-lookup"><span data-stu-id="df069-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="df069-129">string</span><span class="sxs-lookup"><span data-stu-id="df069-129">string</span></span> | <span data-ttu-id="df069-130">Indica si la actividad la realizó un administrador</span><span class="sxs-lookup"><span data-stu-id="df069-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="df069-131">string</span><span class="sxs-lookup"><span data-stu-id="df069-131">string</span></span> | <span data-ttu-id="df069-132">Tipo de dispositivo basado en propósito y funcionalidad, como "Dispositivo de red", "Estación de trabajo", "Servidor", "Móvil", "Consola de juegos" o "Impresora"</span><span class="sxs-lookup"><span data-stu-id="df069-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="df069-133">string</span><span class="sxs-lookup"><span data-stu-id="df069-133">string</span></span> | <span data-ttu-id="df069-134">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="df069-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="df069-135">Esta columna indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="df069-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="df069-136">string</span><span class="sxs-lookup"><span data-stu-id="df069-136">string</span></span> | <span data-ttu-id="df069-137">Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="df069-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="df069-138">string</span><span class="sxs-lookup"><span data-stu-id="df069-138">string</span></span> | <span data-ttu-id="df069-139">Indica si la dirección IP pertenece a un proxy anónimo conocido</span><span class="sxs-lookup"><span data-stu-id="df069-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="df069-140">string</span><span class="sxs-lookup"><span data-stu-id="df069-140">string</span></span> | <span data-ttu-id="df069-141">Código de dos letras que indica el país donde se geolocalización la dirección IP del cliente</span><span class="sxs-lookup"><span data-stu-id="df069-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="df069-142">string</span><span class="sxs-lookup"><span data-stu-id="df069-142">string</span></span> | <span data-ttu-id="df069-143">Ciudad donde la dirección IP del cliente está geolocalada</span><span class="sxs-lookup"><span data-stu-id="df069-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="df069-144">string</span><span class="sxs-lookup"><span data-stu-id="df069-144">string</span></span> | <span data-ttu-id="df069-145">Proveedor de servicios de Internet (ISP) asociado a la dirección IP</span><span class="sxs-lookup"><span data-stu-id="df069-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="df069-146">string</span><span class="sxs-lookup"><span data-stu-id="df069-146">string</span></span> | <span data-ttu-id="df069-147">Información de agente de usuario del explorador web u otra aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="df069-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="df069-148">string</span><span class="sxs-lookup"><span data-stu-id="df069-148">string</span></span> | <span data-ttu-id="df069-149">Tipo de actividad que desencadenó el evento</span><span class="sxs-lookup"><span data-stu-id="df069-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="df069-150">string</span><span class="sxs-lookup"><span data-stu-id="df069-150">string</span></span> | <span data-ttu-id="df069-151">Lista de objetos, como archivos o carpetas, que participaron en la actividad registrada</span><span class="sxs-lookup"><span data-stu-id="df069-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="df069-152">string</span><span class="sxs-lookup"><span data-stu-id="df069-152">string</span></span> | <span data-ttu-id="df069-153">Nombre del objeto al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="df069-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="df069-154">string</span><span class="sxs-lookup"><span data-stu-id="df069-154">string</span></span> | <span data-ttu-id="df069-155">Tipo de objeto, como un archivo o una carpeta, al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="df069-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="df069-156">string</span><span class="sxs-lookup"><span data-stu-id="df069-156">string</span></span> | <span data-ttu-id="df069-157">Identificador único del objeto al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="df069-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="df069-158">string</span><span class="sxs-lookup"><span data-stu-id="df069-158">string</span></span> | <span data-ttu-id="df069-159">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="df069-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="df069-160">string</span><span class="sxs-lookup"><span data-stu-id="df069-160">string</span></span> | <span data-ttu-id="df069-161">Información de evento sin procesar de la aplicación o servicio de origen en formato JSON</span><span class="sxs-lookup"><span data-stu-id="df069-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="df069-162">string</span><span class="sxs-lookup"><span data-stu-id="df069-162">string</span></span> | <span data-ttu-id="df069-163">Información adicional sobre la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="df069-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="df069-164">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="df069-164">Related topics</span></span>
- [<span data-ttu-id="df069-165">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="df069-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="df069-166">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="df069-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="df069-167">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="df069-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="df069-168">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="df069-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="df069-169">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="df069-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="df069-170">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="df069-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
