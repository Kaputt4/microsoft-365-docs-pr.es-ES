---
title: Tabla AppFileEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre eventos relacionados con archivos asociados con servicios y aplicaciones en la nube en la tabla AppFileEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 8406d1f9e3d56555b1699d191933c6f9735c9574
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145492"
---
# <a name="appfileevents"></a><span data-ttu-id="0c1a4-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="0c1a4-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0c1a4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0c1a4-105">**Applies to:**</span></span>
- <span data-ttu-id="0c1a4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c1a4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0c1a4-107">La tabla del esquema de búsqueda avanzada contiene información sobre las actividades relacionadas con archivos en aplicaciones y servicios en la nube `AppFileEvents` supervisados por Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0c1a4-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="0c1a4-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="0c1a4-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="0c1a4-109">Para obtener información detallada acerca de los tipos de eventos (valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="0c1a4-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="0c1a4-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0c1a4-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0c1a4-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="0c1a4-111">Column name</span></span> | <span data-ttu-id="0c1a4-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0c1a4-112">Data type</span></span> | <span data-ttu-id="0c1a4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c1a4-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0c1a4-114">datetime</span><span class="sxs-lookup"><span data-stu-id="0c1a4-114">datetime</span></span> | <span data-ttu-id="0c1a4-115">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="0c1a4-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0c1a4-116">cadena</span><span class="sxs-lookup"><span data-stu-id="0c1a4-116">string</span></span> | <span data-ttu-id="0c1a4-117">Tipo de actividad que desencadenó el evento.</span><span class="sxs-lookup"><span data-stu-id="0c1a4-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="0c1a4-118">Consulta la [referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información</span><span class="sxs-lookup"><span data-stu-id="0c1a4-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="0c1a4-119">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-119">string</span></span> | <span data-ttu-id="0c1a4-120">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="0c1a4-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="0c1a4-121">cadena</span><span class="sxs-lookup"><span data-stu-id="0c1a4-121">string</span></span> | <span data-ttu-id="0c1a4-122">Nombre del archivo donde se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="0c1a4-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="0c1a4-123">cadena</span><span class="sxs-lookup"><span data-stu-id="0c1a4-123">string</span></span> | <span data-ttu-id="0c1a4-124">Carpeta que contiene el archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="0c1a4-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="0c1a4-125">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-125">string</span></span> | <span data-ttu-id="0c1a4-126">Nombre original del archivo cuyo nombre se cambió como resultado de la acción</span><span class="sxs-lookup"><span data-stu-id="0c1a4-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="0c1a4-127">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-127">string</span></span> | <span data-ttu-id="0c1a4-128">Carpeta original que contiene el archivo antes de aplicar la acción grabada</span><span class="sxs-lookup"><span data-stu-id="0c1a4-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="0c1a4-129">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-129">string</span></span> | <span data-ttu-id="0c1a4-130">Protocolo de red usado</span><span class="sxs-lookup"><span data-stu-id="0c1a4-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="0c1a4-131">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-131">string</span></span> | <span data-ttu-id="0c1a4-132">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="0c1a4-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0c1a4-133">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-133">string</span></span> | <span data-ttu-id="0c1a4-134">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="0c1a4-134">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="0c1a4-135">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-135">string</span></span> | <span data-ttu-id="0c1a4-136">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="0c1a4-136">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="0c1a4-137">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-137">string</span></span> | <span data-ttu-id="0c1a4-138">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="0c1a4-138">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0c1a4-139">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-139">string</span></span> | <span data-ttu-id="0c1a4-140">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="0c1a4-140">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0c1a4-141">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-141">string</span></span> | <span data-ttu-id="0c1a4-142">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="0c1a4-142">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0c1a4-143">Normalmente, una combinación de un nombre o nombre, una iniciación intermedia y un apellido o apellido.</span><span class="sxs-lookup"><span data-stu-id="0c1a4-143">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="0c1a4-144">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-144">string</span></span> | <span data-ttu-id="0c1a4-145">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="0c1a4-145">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="0c1a4-146">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-146">string</span></span> | <span data-ttu-id="0c1a4-147">Tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0c1a4-147">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="0c1a4-148">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-148">string</span></span> | <span data-ttu-id="0c1a4-149">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c1a4-149">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0c1a4-150">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0c1a4-150">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="0c1a4-151">cadena</span><span class="sxs-lookup"><span data-stu-id="0c1a4-151">string</span></span> | <span data-ttu-id="0c1a4-152">Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="0c1a4-152">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="0c1a4-153">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-153">string</span></span> | <span data-ttu-id="0c1a4-154">Puerto TCP usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="0c1a4-154">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="0c1a4-155">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-155">string</span></span> | <span data-ttu-id="0c1a4-156">Nombre del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="0c1a4-156">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="0c1a4-157">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-157">string</span></span> | <span data-ttu-id="0c1a4-158">Dirección IP del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="0c1a4-158">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="0c1a4-159">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-159">string</span></span> | <span data-ttu-id="0c1a4-160">Puerto de destino de comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="0c1a4-160">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="0c1a4-161">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-161">string</span></span> | <span data-ttu-id="0c1a4-162">Ciudad, país u otra ubicación geográfica asociada al evento</span><span class="sxs-lookup"><span data-stu-id="0c1a4-162">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="0c1a4-163">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-163">string</span></span> | <span data-ttu-id="0c1a4-164">Proveedor de servicios de Internet (ISP) asociado a la dirección IP del extremo</span><span class="sxs-lookup"><span data-stu-id="0c1a4-164">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="0c1a4-165">largo</span><span class="sxs-lookup"><span data-stu-id="0c1a4-165">long</span></span> | <span data-ttu-id="0c1a4-166">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="0c1a4-166">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="0c1a4-167">string</span><span class="sxs-lookup"><span data-stu-id="0c1a4-167">string</span></span> | <span data-ttu-id="0c1a4-168">Información adicional sobre la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="0c1a4-168">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0c1a4-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0c1a4-169">Related topics</span></span>
- [<span data-ttu-id="0c1a4-170">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="0c1a4-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0c1a4-171">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="0c1a4-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0c1a4-172">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="0c1a4-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0c1a4-173">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="0c1a4-173">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0c1a4-174">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="0c1a4-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0c1a4-175">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="0c1a4-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
