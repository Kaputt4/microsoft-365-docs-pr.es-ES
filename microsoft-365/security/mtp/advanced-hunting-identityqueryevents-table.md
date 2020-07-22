---
title: Tabla IdentityQueryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de consulta de Active Directory en la tabla IdentityQueryEvents del esquema de búsqueda avanzada.
keywords: caza avanzado, cazar amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityQueryEvents, Azure AD, Active Directory, ATP de Azure, identidades, consultas LDAP
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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204880"
---
# <a name="identityqueryevents"></a><span data-ttu-id="c640c-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="c640c-104">IdentityQueryEvents</span></span>

<span data-ttu-id="c640c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c640c-105">**Applies to:**</span></span>
- <span data-ttu-id="c640c-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c640c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c640c-107">La `IdentityQueryEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las consultas realizadas en objetos de Active Directory, como usuarios, grupos, dispositivos y dominios.</span><span class="sxs-lookup"><span data-stu-id="c640c-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="c640c-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="c640c-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c640c-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c640c-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c640c-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="c640c-110">Column name</span></span> | <span data-ttu-id="c640c-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c640c-111">Data type</span></span> | <span data-ttu-id="c640c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c640c-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c640c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c640c-113">datetime</span></span> | <span data-ttu-id="c640c-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="c640c-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="c640c-115">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-115">string</span></span> | <span data-ttu-id="c640c-116">Tipo de actividad que ha desencadenado el evento</span><span class="sxs-lookup"><span data-stu-id="c640c-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="c640c-117">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-117">string</span></span> | <span data-ttu-id="c640c-118">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="c640c-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="c640c-119">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-119">string</span></span> | <span data-ttu-id="c640c-120">Tipo de consulta, como QueryGroup, QueryUser o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="c640c-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="c640c-121">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-121">string</span></span> | <span data-ttu-id="c640c-122">Nombre del usuario, grupo, dispositivo, dominio o cualquier otro tipo de entidad consultado</span><span class="sxs-lookup"><span data-stu-id="c640c-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="c640c-123">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-123">string</span></span> | <span data-ttu-id="c640c-124">Cadena que se usa para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="c640c-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="c640c-125">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-125">string</span></span> | <span data-ttu-id="c640c-126">Protocolo usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="c640c-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="c640c-127">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-127">string</span></span> | <span data-ttu-id="c640c-128">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="c640c-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c640c-129">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-129">string</span></span> | <span data-ttu-id="c640c-130">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="c640c-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="c640c-131">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-131">string</span></span> | <span data-ttu-id="c640c-132">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="c640c-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="c640c-133">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-133">string</span></span> | <span data-ttu-id="c640c-134">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="c640c-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="c640c-135">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-135">string</span></span> | <span data-ttu-id="c640c-136">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="c640c-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c640c-137">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-137">string</span></span> | <span data-ttu-id="c640c-138">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="c640c-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c640c-139">Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido.</span><span class="sxs-lookup"><span data-stu-id="c640c-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="c640c-140">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-140">string</span></span> | <span data-ttu-id="c640c-141">Nombre de dominio completo (FQDN) del extremo</span><span class="sxs-lookup"><span data-stu-id="c640c-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="c640c-142">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-142">string</span></span> | <span data-ttu-id="c640c-143">Dirección IP asignada al extremo y utilizada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="c640c-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="c640c-144">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-144">string</span></span> | <span data-ttu-id="c640c-145">Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="c640c-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="c640c-146">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-146">string</span></span> | <span data-ttu-id="c640c-147">Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="c640c-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="c640c-148">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-148">string</span></span> | <span data-ttu-id="c640c-149">Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="c640c-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="c640c-150">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-150">string</span></span> | <span data-ttu-id="c640c-151">Nombre principal de usuario (UPN) de la cuenta a la que se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="c640c-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="c640c-152">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-152">string</span></span> | <span data-ttu-id="c640c-153">Nombre para mostrar de la cuenta a la que se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="c640c-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="c640c-154">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-154">string</span></span> | <span data-ttu-id="c640c-155">Ciudad, país u otra ubicación geográfica asociada con el evento</span><span class="sxs-lookup"><span data-stu-id="c640c-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="c640c-156">largo</span><span class="sxs-lookup"><span data-stu-id="c640c-156">long</span></span> | <span data-ttu-id="c640c-157">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="c640c-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="c640c-158">cadena</span><span class="sxs-lookup"><span data-stu-id="c640c-158">string</span></span> | <span data-ttu-id="c640c-159">Información adicional acerca de la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="c640c-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c640c-160">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c640c-160">Related topics</span></span>
- [<span data-ttu-id="c640c-161">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c640c-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c640c-162">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="c640c-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c640c-163">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="c640c-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c640c-164">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c640c-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c640c-165">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="c640c-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c640c-166">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="c640c-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
