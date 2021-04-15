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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83b9eec37648ba48aa8e6931e836e8a5e22458c8
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760031"
---
# <a name="cloudappevents"></a><span data-ttu-id="565f1-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="565f1-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="565f1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="565f1-105">**Applies to:**</span></span>
- <span data-ttu-id="565f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="565f1-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="565f1-107">La tabla del esquema de búsqueda avanzada contiene información sobre las actividades en diversas aplicaciones y servicios en la nube `CloudAppEvents` cubiertos por Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="565f1-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="565f1-108">Para obtener una lista completa, vaya a [Aplicaciones y servicios cubiertos.](#apps-and-services-covered)</span><span class="sxs-lookup"><span data-stu-id="565f1-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="565f1-109">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="565f1-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="565f1-110">Esta tabla incluye información que solía estar disponible en la `AppFileEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="565f1-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="565f1-111">A partir del 7 de marzo de 2021, los usuarios que usen actividades relacionadas con archivos en servicios en la nube en y más allá de esta fecha deben usar la `CloudAppEvents` tabla en su lugar.</span><span class="sxs-lookup"><span data-stu-id="565f1-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="565f1-112">Asegúrese de buscar consultas y reglas de detección personalizadas que aún usan la tabla y `AppFileEvents` editarlas para usar la `CloudAppEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="565f1-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="565f1-113">Encontrará más instrucciones sobre la conversión de consultas afectadas en [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span><span class="sxs-lookup"><span data-stu-id="565f1-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="565f1-114">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="565f1-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="565f1-115">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="565f1-115">Column name</span></span> | <span data-ttu-id="565f1-116">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="565f1-116">Data type</span></span> | <span data-ttu-id="565f1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="565f1-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="565f1-118">datetime</span><span class="sxs-lookup"><span data-stu-id="565f1-118">datetime</span></span> | <span data-ttu-id="565f1-119">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="565f1-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="565f1-120">cadena</span><span class="sxs-lookup"><span data-stu-id="565f1-120">string</span></span> | <span data-ttu-id="565f1-121">Tipo de actividad que desencadenó el evento</span><span class="sxs-lookup"><span data-stu-id="565f1-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="565f1-122">string</span><span class="sxs-lookup"><span data-stu-id="565f1-122">string</span></span> | <span data-ttu-id="565f1-123">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="565f1-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="565f1-124">string</span><span class="sxs-lookup"><span data-stu-id="565f1-124">string</span></span> | <span data-ttu-id="565f1-125">Identificador único de la aplicación</span><span class="sxs-lookup"><span data-stu-id="565f1-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="565f1-126">string</span><span class="sxs-lookup"><span data-stu-id="565f1-126">string</span></span> | <span data-ttu-id="565f1-127">Identificador único de la cuenta en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="565f1-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="565f1-128">string</span><span class="sxs-lookup"><span data-stu-id="565f1-128">string</span></span> | <span data-ttu-id="565f1-129">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="565f1-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="565f1-130">Normalmente, una combinación de un nombre o un nombre determinado, un inicio intermedio y un apellido o apellido.</span><span class="sxs-lookup"><span data-stu-id="565f1-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="565f1-131">string</span><span class="sxs-lookup"><span data-stu-id="565f1-131">string</span></span> | <span data-ttu-id="565f1-132">Indica si la actividad la realizó un administrador</span><span class="sxs-lookup"><span data-stu-id="565f1-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="565f1-133">string</span><span class="sxs-lookup"><span data-stu-id="565f1-133">string</span></span> | <span data-ttu-id="565f1-134">Tipo de dispositivo basado en propósitos y funciones, como "Dispositivo de red", "Estación de trabajo", "Servidor", "Móvil", "Consola de juegos" o "Impresora"</span><span class="sxs-lookup"><span data-stu-id="565f1-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="565f1-135">string</span><span class="sxs-lookup"><span data-stu-id="565f1-135">string</span></span> | <span data-ttu-id="565f1-136">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="565f1-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="565f1-137">Esta columna indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="565f1-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="565f1-138">string</span><span class="sxs-lookup"><span data-stu-id="565f1-138">string</span></span> | <span data-ttu-id="565f1-139">Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="565f1-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="565f1-140">string</span><span class="sxs-lookup"><span data-stu-id="565f1-140">string</span></span> | <span data-ttu-id="565f1-141">Indica si la dirección IP pertenece a un proxy anónimo conocido</span><span class="sxs-lookup"><span data-stu-id="565f1-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="565f1-142">string</span><span class="sxs-lookup"><span data-stu-id="565f1-142">string</span></span> | <span data-ttu-id="565f1-143">Código de dos letras que indica el país donde se geolocalización de la dirección IP del cliente</span><span class="sxs-lookup"><span data-stu-id="565f1-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="565f1-144">string</span><span class="sxs-lookup"><span data-stu-id="565f1-144">string</span></span> | <span data-ttu-id="565f1-145">Ciudad donde se geolocalización de la dirección IP del cliente</span><span class="sxs-lookup"><span data-stu-id="565f1-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="565f1-146">string</span><span class="sxs-lookup"><span data-stu-id="565f1-146">string</span></span> | <span data-ttu-id="565f1-147">Proveedor de servicios de Internet (ISP) asociado a la dirección IP</span><span class="sxs-lookup"><span data-stu-id="565f1-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="565f1-148">string</span><span class="sxs-lookup"><span data-stu-id="565f1-148">string</span></span> | <span data-ttu-id="565f1-149">Información del agente de usuario desde el explorador web u otra aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="565f1-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="565f1-150">string</span><span class="sxs-lookup"><span data-stu-id="565f1-150">string</span></span> | <span data-ttu-id="565f1-151">Tipo de actividad que desencadenó el evento</span><span class="sxs-lookup"><span data-stu-id="565f1-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="565f1-152">string</span><span class="sxs-lookup"><span data-stu-id="565f1-152">string</span></span> | <span data-ttu-id="565f1-153">Lista de objetos, como archivos o carpetas, que participaron en la actividad grabada</span><span class="sxs-lookup"><span data-stu-id="565f1-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="565f1-154">string</span><span class="sxs-lookup"><span data-stu-id="565f1-154">string</span></span> | <span data-ttu-id="565f1-155">Nombre del objeto al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="565f1-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="565f1-156">string</span><span class="sxs-lookup"><span data-stu-id="565f1-156">string</span></span> | <span data-ttu-id="565f1-157">Tipo de objeto, como un archivo o una carpeta, al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="565f1-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="565f1-158">string</span><span class="sxs-lookup"><span data-stu-id="565f1-158">string</span></span> | <span data-ttu-id="565f1-159">Identificador único del objeto al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="565f1-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="565f1-160">string</span><span class="sxs-lookup"><span data-stu-id="565f1-160">string</span></span> | <span data-ttu-id="565f1-161">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="565f1-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="565f1-162">string</span><span class="sxs-lookup"><span data-stu-id="565f1-162">string</span></span> | <span data-ttu-id="565f1-163">Información de evento sin procesar de la aplicación o servicio de origen en formato JSON</span><span class="sxs-lookup"><span data-stu-id="565f1-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="565f1-164">string</span><span class="sxs-lookup"><span data-stu-id="565f1-164">string</span></span> | <span data-ttu-id="565f1-165">Información adicional sobre la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="565f1-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="565f1-166">Aplicaciones y servicios cubiertos</span><span class="sxs-lookup"><span data-stu-id="565f1-166">Apps and services covered</span></span>

- <span data-ttu-id="565f1-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="565f1-167">Dropbox</span></span>
- <span data-ttu-id="565f1-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="565f1-168">Dynamics 365</span></span>
- <span data-ttu-id="565f1-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="565f1-169">Exchange Online</span></span>
- <span data-ttu-id="565f1-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="565f1-170">Microsoft Teams</span></span>
- <span data-ttu-id="565f1-171">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="565f1-171">OneDrive for Business</span></span>
- <span data-ttu-id="565f1-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="565f1-172">Power Automate</span></span>
- <span data-ttu-id="565f1-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="565f1-173">Power BI</span></span>
- <span data-ttu-id="565f1-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="565f1-174">SharePoint Online</span></span>
- <span data-ttu-id="565f1-175">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="565f1-175">Skype for Business</span></span>
- <span data-ttu-id="565f1-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="565f1-176">Office 365</span></span>
- <span data-ttu-id="565f1-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="565f1-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="565f1-178">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="565f1-178">Related topics</span></span>
- [<span data-ttu-id="565f1-179">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="565f1-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="565f1-180">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="565f1-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="565f1-181">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="565f1-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="565f1-182">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="565f1-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="565f1-183">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="565f1-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="565f1-184">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="565f1-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
