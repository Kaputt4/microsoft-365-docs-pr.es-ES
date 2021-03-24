---
title: Tabla CloudAppEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre eventos de servicios y aplicaciones en la nube en la tabla CloudAppEvents del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, CloudAppEvents, Cloud App Security, MCAS
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e9e9cc78289136e22da1871d68a384eac2a901ef
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071592"
---
# <a name="cloudappevents"></a><span data-ttu-id="ed4c4-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="ed4c4-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ed4c4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ed4c4-105">**Applies to:**</span></span>
- <span data-ttu-id="ed4c4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed4c4-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="ed4c4-107">La tabla del esquema de búsqueda avanzada contiene información sobre las actividades en diversas aplicaciones y servicios en la nube que cubre Microsoft Cloud App Security, específicamente `CloudAppEvents` Dropbox, [](advanced-hunting-overview.md) Exchange Online, OneDrive, Microsoft Teams y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="ed4c4-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ed4c4-109">Esta tabla incluye información que solía estar disponible en la `AppFileEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="ed4c4-110">A partir del 7 de marzo de 2021, los usuarios que usen actividades relacionadas con archivos en servicios en la nube en y más allá de esta fecha deben usar la `CloudAppEvents` tabla en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="ed4c4-111">Asegúrese de buscar consultas y reglas de detección personalizadas que aún usan la tabla y `AppFileEvents` editarlas para usar la `CloudAppEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="ed4c4-112">Encontrará más instrucciones sobre la conversión de consultas afectadas en [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span><span class="sxs-lookup"><span data-stu-id="ed4c4-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="ed4c4-113">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ed4c4-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ed4c4-114">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="ed4c4-114">Column name</span></span> | <span data-ttu-id="ed4c4-115">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ed4c4-115">Data type</span></span> | <span data-ttu-id="ed4c4-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed4c4-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ed4c4-117">datetime</span><span class="sxs-lookup"><span data-stu-id="ed4c4-117">datetime</span></span> | <span data-ttu-id="ed4c4-118">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="ed4c4-119">cadena</span><span class="sxs-lookup"><span data-stu-id="ed4c4-119">string</span></span> | <span data-ttu-id="ed4c4-120">Tipo de actividad que desencadenó el evento</span><span class="sxs-lookup"><span data-stu-id="ed4c4-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="ed4c4-121">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-121">string</span></span> | <span data-ttu-id="ed4c4-122">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="ed4c4-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="ed4c4-123">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-123">string</span></span> | <span data-ttu-id="ed4c4-124">Identificador único de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ed4c4-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="ed4c4-125">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-125">string</span></span> | <span data-ttu-id="ed4c4-126">Identificador único de la cuenta en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ed4c4-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="ed4c4-127">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-127">string</span></span> | <span data-ttu-id="ed4c4-128">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="ed4c4-129">Normalmente, una combinación de un nombre o un nombre determinado, un inicio intermedio y un apellido o apellido.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="ed4c4-130">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-130">string</span></span> | <span data-ttu-id="ed4c4-131">Indica si la actividad la realizó un administrador</span><span class="sxs-lookup"><span data-stu-id="ed4c4-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="ed4c4-132">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-132">string</span></span> | <span data-ttu-id="ed4c4-133">Tipo de dispositivo basado en propósitos y funciones, como "Dispositivo de red", "Estación de trabajo", "Servidor", "Móvil", "Consola de juegos" o "Impresora"</span><span class="sxs-lookup"><span data-stu-id="ed4c4-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="ed4c4-134">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-134">string</span></span> | <span data-ttu-id="ed4c4-135">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="ed4c4-136">Esta columna indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="ed4c4-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="ed4c4-137">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-137">string</span></span> | <span data-ttu-id="ed4c4-138">Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="ed4c4-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="ed4c4-139">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-139">string</span></span> | <span data-ttu-id="ed4c4-140">Indica si la dirección IP pertenece a un proxy anónimo conocido</span><span class="sxs-lookup"><span data-stu-id="ed4c4-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="ed4c4-141">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-141">string</span></span> | <span data-ttu-id="ed4c4-142">Código de dos letras que indica el país donde se geolocalización de la dirección IP del cliente</span><span class="sxs-lookup"><span data-stu-id="ed4c4-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="ed4c4-143">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-143">string</span></span> | <span data-ttu-id="ed4c4-144">Ciudad donde se geolocalización de la dirección IP del cliente</span><span class="sxs-lookup"><span data-stu-id="ed4c4-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="ed4c4-145">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-145">string</span></span> | <span data-ttu-id="ed4c4-146">Proveedor de servicios de Internet (ISP) asociado a la dirección IP</span><span class="sxs-lookup"><span data-stu-id="ed4c4-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="ed4c4-147">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-147">string</span></span> | <span data-ttu-id="ed4c4-148">Información del agente de usuario desde el explorador web u otra aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="ed4c4-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="ed4c4-149">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-149">string</span></span> | <span data-ttu-id="ed4c4-150">Tipo de actividad que desencadenó el evento</span><span class="sxs-lookup"><span data-stu-id="ed4c4-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="ed4c4-151">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-151">string</span></span> | <span data-ttu-id="ed4c4-152">Lista de objetos, como archivos o carpetas, que participaron en la actividad grabada</span><span class="sxs-lookup"><span data-stu-id="ed4c4-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="ed4c4-153">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-153">string</span></span> | <span data-ttu-id="ed4c4-154">Nombre del objeto al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="ed4c4-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="ed4c4-155">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-155">string</span></span> | <span data-ttu-id="ed4c4-156">Tipo de objeto, como un archivo o una carpeta, al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="ed4c4-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="ed4c4-157">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-157">string</span></span> | <span data-ttu-id="ed4c4-158">Identificador único del objeto al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="ed4c4-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="ed4c4-159">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-159">string</span></span> | <span data-ttu-id="ed4c4-160">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="ed4c4-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="ed4c4-161">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-161">string</span></span> | <span data-ttu-id="ed4c4-162">Información de evento sin procesar de la aplicación o servicio de origen en formato JSON</span><span class="sxs-lookup"><span data-stu-id="ed4c4-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="ed4c4-163">string</span><span class="sxs-lookup"><span data-stu-id="ed4c4-163">string</span></span> | <span data-ttu-id="ed4c4-164">Información adicional sobre la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="ed4c4-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="ed4c4-165">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ed4c4-165">Related topics</span></span>
- [<span data-ttu-id="ed4c4-166">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="ed4c4-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ed4c4-167">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="ed4c4-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ed4c4-168">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="ed4c4-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ed4c4-169">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="ed4c4-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ed4c4-170">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="ed4c4-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ed4c4-171">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="ed4c4-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
