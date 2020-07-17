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
ms.openlocfilehash: bec7f13d49e2ccf4e3a9121d5e5a2fecd1b10aa2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899118"
---
# <a name="identityqueryevents"></a><span data-ttu-id="1159d-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="1159d-104">IdentityQueryEvents</span></span>

<span data-ttu-id="1159d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1159d-105">**Applies to:**</span></span>
- <span data-ttu-id="1159d-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1159d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1159d-107">La `IdentityQueryEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las consultas realizadas en objetos de Active Directory, como usuarios, grupos, dispositivos y dominios.</span><span class="sxs-lookup"><span data-stu-id="1159d-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="1159d-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="1159d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="1159d-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1159d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1159d-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="1159d-110">Column name</span></span> | <span data-ttu-id="1159d-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1159d-111">Data type</span></span> | <span data-ttu-id="1159d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1159d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="1159d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="1159d-113">datetime</span></span> | <span data-ttu-id="1159d-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="1159d-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="1159d-115">cadena</span><span class="sxs-lookup"><span data-stu-id="1159d-115">string</span></span> | <span data-ttu-id="1159d-116">Tipo de actividad que ha desencadenado el evento</span><span class="sxs-lookup"><span data-stu-id="1159d-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="1159d-117">string</span><span class="sxs-lookup"><span data-stu-id="1159d-117">string</span></span> | <span data-ttu-id="1159d-118">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="1159d-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="1159d-119">string</span><span class="sxs-lookup"><span data-stu-id="1159d-119">string</span></span> | <span data-ttu-id="1159d-120">Tipo de consulta: QueryGroup, QueryUser o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="1159d-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="1159d-121">string</span><span class="sxs-lookup"><span data-stu-id="1159d-121">string</span></span> | <span data-ttu-id="1159d-122">Nombre del usuario, grupo, dispositivo, dominio o cualquier otro tipo de entidad consultado</span><span class="sxs-lookup"><span data-stu-id="1159d-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="1159d-123">string</span><span class="sxs-lookup"><span data-stu-id="1159d-123">string</span></span> | <span data-ttu-id="1159d-124">Protocolo usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="1159d-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="1159d-125">string</span><span class="sxs-lookup"><span data-stu-id="1159d-125">string</span></span> | <span data-ttu-id="1159d-126">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="1159d-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="1159d-127">string</span><span class="sxs-lookup"><span data-stu-id="1159d-127">string</span></span> | <span data-ttu-id="1159d-128">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="1159d-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="1159d-129">string</span><span class="sxs-lookup"><span data-stu-id="1159d-129">string</span></span> | <span data-ttu-id="1159d-130">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="1159d-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="1159d-131">string</span><span class="sxs-lookup"><span data-stu-id="1159d-131">string</span></span> | <span data-ttu-id="1159d-132">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="1159d-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="1159d-133">string</span><span class="sxs-lookup"><span data-stu-id="1159d-133">string</span></span> | <span data-ttu-id="1159d-134">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="1159d-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="1159d-135">string</span><span class="sxs-lookup"><span data-stu-id="1159d-135">string</span></span> | <span data-ttu-id="1159d-136">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="1159d-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="1159d-137">Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido.</span><span class="sxs-lookup"><span data-stu-id="1159d-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="1159d-138">string</span><span class="sxs-lookup"><span data-stu-id="1159d-138">string</span></span> | <span data-ttu-id="1159d-139">Nombre de dominio completo (FQDN) del extremo</span><span class="sxs-lookup"><span data-stu-id="1159d-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="1159d-140">string</span><span class="sxs-lookup"><span data-stu-id="1159d-140">string</span></span> | <span data-ttu-id="1159d-141">Dirección IP asignada al extremo y utilizada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="1159d-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="1159d-142">string</span><span class="sxs-lookup"><span data-stu-id="1159d-142">string</span></span> | <span data-ttu-id="1159d-143">Ciudad, país u otra ubicación geográfica asociada con el evento</span><span class="sxs-lookup"><span data-stu-id="1159d-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1159d-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1159d-144">Related topics</span></span>
- [<span data-ttu-id="1159d-145">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="1159d-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1159d-146">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="1159d-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1159d-147">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="1159d-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1159d-148">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="1159d-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1159d-149">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="1159d-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1159d-150">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="1159d-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
