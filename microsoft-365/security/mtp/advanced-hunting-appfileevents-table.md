---
title: Tabla AppFileEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre eventos relacionados con archivos asociados con aplicaciones y servicios en la nube en la tabla AppFileEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AppFileEvents, Cloud App Security, MCAS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 5cab6e3fe7a3b4b74989dde360c03d58e0bad46f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430156"
---
# <a name="appfileevents"></a><span data-ttu-id="87c89-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="87c89-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="87c89-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="87c89-105">**Applies to:**</span></span>
- <span data-ttu-id="87c89-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="87c89-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="87c89-107">La `AppFileEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre actividades relacionadas con archivos en aplicaciones en la nube y servicios supervisados por Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="87c89-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="87c89-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="87c89-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="87c89-109">Para obtener información detallada acerca de los tipos de eventos ( `ActionType` valores) admitidos por una tabla, use la [referencia de esquema integrada](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponible en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="87c89-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="87c89-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="87c89-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="87c89-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="87c89-111">Column name</span></span> | <span data-ttu-id="87c89-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="87c89-112">Data type</span></span> | <span data-ttu-id="87c89-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="87c89-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="87c89-114">datetime</span><span class="sxs-lookup"><span data-stu-id="87c89-114">datetime</span></span> | <span data-ttu-id="87c89-115">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="87c89-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="87c89-116">cadena</span><span class="sxs-lookup"><span data-stu-id="87c89-116">string</span></span> | <span data-ttu-id="87c89-117">Tipo de actividad que ha desencadenado el evento.</span><span class="sxs-lookup"><span data-stu-id="87c89-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="87c89-118">Consulte la [Referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más detalles</span><span class="sxs-lookup"><span data-stu-id="87c89-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="87c89-119">string</span><span class="sxs-lookup"><span data-stu-id="87c89-119">string</span></span> | <span data-ttu-id="87c89-120">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="87c89-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="87c89-121">cadena</span><span class="sxs-lookup"><span data-stu-id="87c89-121">string</span></span> | <span data-ttu-id="87c89-122">Nombre del archivo donde se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="87c89-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="87c89-123">cadena</span><span class="sxs-lookup"><span data-stu-id="87c89-123">string</span></span> | <span data-ttu-id="87c89-124">Carpeta que contiene el archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="87c89-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="87c89-125">string</span><span class="sxs-lookup"><span data-stu-id="87c89-125">string</span></span> | <span data-ttu-id="87c89-126">Nombre original del archivo cuyo nombre ha cambiado como resultado de la acción</span><span class="sxs-lookup"><span data-stu-id="87c89-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="87c89-127">string</span><span class="sxs-lookup"><span data-stu-id="87c89-127">string</span></span> | <span data-ttu-id="87c89-128">Carpeta original que contiene el archivo antes de que se haya aplicado la acción grabada</span><span class="sxs-lookup"><span data-stu-id="87c89-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="87c89-129">string</span><span class="sxs-lookup"><span data-stu-id="87c89-129">string</span></span> | <span data-ttu-id="87c89-130">Protocolo de red usado</span><span class="sxs-lookup"><span data-stu-id="87c89-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="87c89-131">string</span><span class="sxs-lookup"><span data-stu-id="87c89-131">string</span></span> | <span data-ttu-id="87c89-132">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="87c89-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="87c89-133">string</span><span class="sxs-lookup"><span data-stu-id="87c89-133">string</span></span> | <span data-ttu-id="87c89-134">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="87c89-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="87c89-135">string</span><span class="sxs-lookup"><span data-stu-id="87c89-135">string</span></span> | <span data-ttu-id="87c89-136">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="87c89-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="87c89-137">string</span><span class="sxs-lookup"><span data-stu-id="87c89-137">string</span></span> | <span data-ttu-id="87c89-138">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="87c89-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="87c89-139">string</span><span class="sxs-lookup"><span data-stu-id="87c89-139">string</span></span> | <span data-ttu-id="87c89-140">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="87c89-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="87c89-141">Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido.</span><span class="sxs-lookup"><span data-stu-id="87c89-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="87c89-142">string</span><span class="sxs-lookup"><span data-stu-id="87c89-142">string</span></span> | <span data-ttu-id="87c89-143">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="87c89-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="87c89-144">string</span><span class="sxs-lookup"><span data-stu-id="87c89-144">string</span></span> | <span data-ttu-id="87c89-145">Tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="87c89-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="87c89-146">string</span><span class="sxs-lookup"><span data-stu-id="87c89-146">string</span></span> | <span data-ttu-id="87c89-147">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="87c89-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="87c89-148">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="87c89-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="87c89-149">cadena</span><span class="sxs-lookup"><span data-stu-id="87c89-149">string</span></span> | <span data-ttu-id="87c89-150">Dirección IP asignada al extremo y utilizada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="87c89-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="87c89-151">string</span><span class="sxs-lookup"><span data-stu-id="87c89-151">string</span></span> | <span data-ttu-id="87c89-152">Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="87c89-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="87c89-153">string</span><span class="sxs-lookup"><span data-stu-id="87c89-153">string</span></span> | <span data-ttu-id="87c89-154">Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="87c89-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="87c89-155">string</span><span class="sxs-lookup"><span data-stu-id="87c89-155">string</span></span> | <span data-ttu-id="87c89-156">Ciudad, país u otra ubicación geográfica asociada con el evento</span><span class="sxs-lookup"><span data-stu-id="87c89-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="87c89-157">string</span><span class="sxs-lookup"><span data-stu-id="87c89-157">string</span></span> | <span data-ttu-id="87c89-158">Proveedor de servicios de Internet (ISP) asociado con la dirección IP del extremo</span><span class="sxs-lookup"><span data-stu-id="87c89-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="87c89-159">largo</span><span class="sxs-lookup"><span data-stu-id="87c89-159">long</span></span> | <span data-ttu-id="87c89-160">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="87c89-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="87c89-161">string</span><span class="sxs-lookup"><span data-stu-id="87c89-161">string</span></span> | <span data-ttu-id="87c89-162">Información adicional acerca de la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="87c89-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="87c89-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="87c89-163">Related topics</span></span>
- [<span data-ttu-id="87c89-164">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="87c89-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="87c89-165">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="87c89-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="87c89-166">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="87c89-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="87c89-167">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="87c89-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="87c89-168">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="87c89-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="87c89-169">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="87c89-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
