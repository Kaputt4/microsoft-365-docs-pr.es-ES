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
ms.openlocfilehash: 7016127a75bca48103f5325ce169faa3d7c31c85
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929819"
---
# <a name="identityqueryevents"></a><span data-ttu-id="b4bdf-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="b4bdf-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b4bdf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b4bdf-105">**Applies to:**</span></span>
- <span data-ttu-id="b4bdf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4bdf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b4bdf-107">La tabla del esquema de búsqueda avanzada contiene información sobre las consultas realizadas en objetos de Active Directory, como `IdentityQueryEvents` usuarios, grupos, dispositivos y dominios. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b4bdf-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="b4bdf-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="b4bdf-109">Para obtener información detallada acerca de los tipos de eventos (valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="b4bdf-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="b4bdf-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b4bdf-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b4bdf-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="b4bdf-111">Column name</span></span> | <span data-ttu-id="b4bdf-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b4bdf-112">Data type</span></span> | <span data-ttu-id="b4bdf-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4bdf-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b4bdf-114">datetime</span><span class="sxs-lookup"><span data-stu-id="b4bdf-114">datetime</span></span> | <span data-ttu-id="b4bdf-115">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="b4bdf-116">cadena</span><span class="sxs-lookup"><span data-stu-id="b4bdf-116">string</span></span> | <span data-ttu-id="b4bdf-117">Tipo de actividad que desencadenó el evento.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="b4bdf-118">Consulta la [referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información</span><span class="sxs-lookup"><span data-stu-id="b4bdf-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="b4bdf-119">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-119">string</span></span> | <span data-ttu-id="b4bdf-120">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="b4bdf-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="b4bdf-121">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-121">string</span></span> | <span data-ttu-id="b4bdf-122">Tipo de consulta, como QueryGroup, QueryUser o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="b4bdf-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="b4bdf-123">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-123">string</span></span> | <span data-ttu-id="b4bdf-124">Nombre del usuario, grupo, dispositivo, dominio o cualquier otro tipo de entidad que se esté consultando</span><span class="sxs-lookup"><span data-stu-id="b4bdf-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="b4bdf-125">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-125">string</span></span> | <span data-ttu-id="b4bdf-126">Cadena usada para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="b4bdf-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="b4bdf-127">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-127">string</span></span> | <span data-ttu-id="b4bdf-128">Protocolo usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="b4bdf-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="b4bdf-129">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-129">string</span></span> | <span data-ttu-id="b4bdf-130">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="b4bdf-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="b4bdf-131">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-131">string</span></span> | <span data-ttu-id="b4bdf-132">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="b4bdf-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="b4bdf-133">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-133">string</span></span> | <span data-ttu-id="b4bdf-134">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="b4bdf-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="b4bdf-135">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-135">string</span></span> | <span data-ttu-id="b4bdf-136">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="b4bdf-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="b4bdf-137">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-137">string</span></span> | <span data-ttu-id="b4bdf-138">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="b4bdf-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="b4bdf-139">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-139">string</span></span> | <span data-ttu-id="b4bdf-140">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="b4bdf-141">Normalmente, una combinación de un nombre o nombre, una iniciación intermedia y un apellido o apellido.</span><span class="sxs-lookup"><span data-stu-id="b4bdf-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="b4bdf-142">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-142">string</span></span> | <span data-ttu-id="b4bdf-143">Nombre de dominio completo (FQDN) del extremo</span><span class="sxs-lookup"><span data-stu-id="b4bdf-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="b4bdf-144">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-144">string</span></span> | <span data-ttu-id="b4bdf-145">Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="b4bdf-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="b4bdf-146">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-146">string</span></span> | <span data-ttu-id="b4bdf-147">Nombre del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="b4bdf-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="b4bdf-148">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-148">string</span></span> | <span data-ttu-id="b4bdf-149">Dirección IP del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="b4bdf-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="b4bdf-150">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-150">string</span></span> | <span data-ttu-id="b4bdf-151">Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="b4bdf-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="b4bdf-152">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-152">string</span></span> | <span data-ttu-id="b4bdf-153">Nombre principal de usuario (UPN) de la cuenta a la que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="b4bdf-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="b4bdf-154">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-154">string</span></span> | <span data-ttu-id="b4bdf-155">Nombre para mostrar de la cuenta a la que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="b4bdf-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="b4bdf-156">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-156">string</span></span> | <span data-ttu-id="b4bdf-157">Ciudad, país u otra ubicación geográfica asociada al evento</span><span class="sxs-lookup"><span data-stu-id="b4bdf-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="b4bdf-158">largo</span><span class="sxs-lookup"><span data-stu-id="b4bdf-158">long</span></span> | <span data-ttu-id="b4bdf-159">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="b4bdf-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="b4bdf-160">string</span><span class="sxs-lookup"><span data-stu-id="b4bdf-160">string</span></span> | <span data-ttu-id="b4bdf-161">Información adicional sobre la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="b4bdf-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b4bdf-162">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b4bdf-162">Related topics</span></span>
- [<span data-ttu-id="b4bdf-163">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="b4bdf-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b4bdf-164">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="b4bdf-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b4bdf-165">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="b4bdf-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b4bdf-166">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="b4bdf-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b4bdf-167">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="b4bdf-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b4bdf-168">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="b4bdf-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
