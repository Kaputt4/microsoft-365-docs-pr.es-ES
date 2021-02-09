---
title: Tabla IdentityQueryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de consulta de Active Directory en la tabla IdentityQueryEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identidades, consultas LDAP
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
ms.openlocfilehash: 48a1520e9fc6239fd3105f01a32a03e5e58df174
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145300"
---
# <a name="identityqueryevents"></a><span data-ttu-id="9e9a1-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="9e9a1-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e9a1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9e9a1-105">**Applies to:**</span></span>
- <span data-ttu-id="9e9a1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e9a1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9e9a1-107">La tabla del esquema de búsqueda avanzada contiene información sobre las consultas realizadas en objetos de Active Directory, como usuarios, grupos, dispositivos `IdentityQueryEvents` y dominios. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9e9a1-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="9e9a1-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9e9a1-109">Para obtener información detallada acerca de los tipos de eventos (valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="9e9a1-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="9e9a1-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9e9a1-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9e9a1-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="9e9a1-111">Column name</span></span> | <span data-ttu-id="9e9a1-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9e9a1-112">Data type</span></span> | <span data-ttu-id="9e9a1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e9a1-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9e9a1-114">datetime</span><span class="sxs-lookup"><span data-stu-id="9e9a1-114">datetime</span></span> | <span data-ttu-id="9e9a1-115">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9e9a1-116">cadena</span><span class="sxs-lookup"><span data-stu-id="9e9a1-116">string</span></span> | <span data-ttu-id="9e9a1-117">Tipo de actividad que desencadenó el evento.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="9e9a1-118">Consulta la [referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información</span><span class="sxs-lookup"><span data-stu-id="9e9a1-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="9e9a1-119">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-119">string</span></span> | <span data-ttu-id="9e9a1-120">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="9e9a1-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="9e9a1-121">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-121">string</span></span> | <span data-ttu-id="9e9a1-122">Tipo de consulta, como QueryGroup, QueryUser o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="9e9a1-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="9e9a1-123">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-123">string</span></span> | <span data-ttu-id="9e9a1-124">Nombre del usuario, grupo, dispositivo, dominio o cualquier otro tipo de entidad que se esté consultando</span><span class="sxs-lookup"><span data-stu-id="9e9a1-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="9e9a1-125">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-125">string</span></span> | <span data-ttu-id="9e9a1-126">Cadena usada para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="9e9a1-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="9e9a1-127">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-127">string</span></span> | <span data-ttu-id="9e9a1-128">Protocolo usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="9e9a1-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="9e9a1-129">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-129">string</span></span> | <span data-ttu-id="9e9a1-130">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9e9a1-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9e9a1-131">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-131">string</span></span> | <span data-ttu-id="9e9a1-132">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9e9a1-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9e9a1-133">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-133">string</span></span> | <span data-ttu-id="9e9a1-134">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9e9a1-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9e9a1-135">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-135">string</span></span> | <span data-ttu-id="9e9a1-136">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9e9a1-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9e9a1-137">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-137">string</span></span> | <span data-ttu-id="9e9a1-138">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="9e9a1-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9e9a1-139">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-139">string</span></span> | <span data-ttu-id="9e9a1-140">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9e9a1-141">Normalmente, una combinación de un nombre o nombre, una iniciación intermedia y un apellido o apellido.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9e9a1-142">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-142">string</span></span> | <span data-ttu-id="9e9a1-143">Nombre de dominio completo (FQDN) del extremo</span><span class="sxs-lookup"><span data-stu-id="9e9a1-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="9e9a1-144">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-144">string</span></span> | <span data-ttu-id="9e9a1-145">Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="9e9a1-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="9e9a1-146">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-146">string</span></span> | <span data-ttu-id="9e9a1-147">Puerto TCP usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="9e9a1-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="9e9a1-148">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-148">string</span></span> | <span data-ttu-id="9e9a1-149">Nombre del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="9e9a1-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="9e9a1-150">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-150">string</span></span> | <span data-ttu-id="9e9a1-151">Dirección IP del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="9e9a1-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="9e9a1-152">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-152">string</span></span> | <span data-ttu-id="9e9a1-153">Puerto de destino de comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="9e9a1-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="9e9a1-154">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-154">string</span></span> | <span data-ttu-id="9e9a1-155">Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="9e9a1-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="9e9a1-156">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-156">string</span></span> | <span data-ttu-id="9e9a1-157">Nombre principal de usuario (UPN) de la cuenta a la que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="9e9a1-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="9e9a1-158">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-158">string</span></span> | <span data-ttu-id="9e9a1-159">Nombre para mostrar de la cuenta a la que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="9e9a1-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="9e9a1-160">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-160">string</span></span> | <span data-ttu-id="9e9a1-161">Ciudad, país u otra ubicación geográfica asociada al evento</span><span class="sxs-lookup"><span data-stu-id="9e9a1-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="9e9a1-162">largo</span><span class="sxs-lookup"><span data-stu-id="9e9a1-162">long</span></span> | <span data-ttu-id="9e9a1-163">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="9e9a1-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="9e9a1-164">string</span><span class="sxs-lookup"><span data-stu-id="9e9a1-164">string</span></span> | <span data-ttu-id="9e9a1-165">Información adicional sobre la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="9e9a1-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9e9a1-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9e9a1-166">Related topics</span></span>
- [<span data-ttu-id="9e9a1-167">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="9e9a1-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9e9a1-168">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="9e9a1-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9e9a1-169">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="9e9a1-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9e9a1-170">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="9e9a1-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9e9a1-171">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="9e9a1-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9e9a1-172">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="9e9a1-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
