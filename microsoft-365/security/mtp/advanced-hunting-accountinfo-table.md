---
title: Tabla AccountInfo en el esquema de búsqueda avanzada
description: Información sobre la cuenta de usuario en la tabla AccountInfo del esquema de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, equipo, usuario, cuenta
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929533"
---
# <a name="accountinfo"></a><span data-ttu-id="555de-104">AccountInfo</span><span class="sxs-lookup"><span data-stu-id="555de-104">AccountInfo</span></span>

<span data-ttu-id="555de-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="555de-105">**Applies to:**</span></span>
- <span data-ttu-id="555de-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="555de-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="555de-107">La `AccountInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las cuentas de usuario obtenidas de varios servicios, incluido Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="555de-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="555de-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="555de-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="555de-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="555de-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="555de-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="555de-110">Column name</span></span> | <span data-ttu-id="555de-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="555de-111">Data type</span></span> | <span data-ttu-id="555de-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="555de-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="555de-113">string</span><span class="sxs-lookup"><span data-stu-id="555de-113">string</span></span> | <span data-ttu-id="555de-114">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="555de-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="555de-115">string</span><span class="sxs-lookup"><span data-stu-id="555de-115">string</span></span> | <span data-ttu-id="555de-116">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="555de-117">string</span><span class="sxs-lookup"><span data-stu-id="555de-117">string</span></span> | <span data-ttu-id="555de-118">Identificador de seguridad local (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="555de-119">string</span><span class="sxs-lookup"><span data-stu-id="555de-119">string</span></span> | <span data-ttu-id="555de-120">Identificador de seguridad en la nube de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="555de-121">string</span><span class="sxs-lookup"><span data-stu-id="555de-121">string</span></span> | <span data-ttu-id="555de-122">Nombre especificado o nombre del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="555de-123">string</span><span class="sxs-lookup"><span data-stu-id="555de-123">string</span></span> | <span data-ttu-id="555de-124">Apellidos, apellidos o familia del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="555de-125">string</span><span class="sxs-lookup"><span data-stu-id="555de-125">string</span></span> | <span data-ttu-id="555de-126">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="555de-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="555de-127">Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido.</span><span class="sxs-lookup"><span data-stu-id="555de-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="555de-128">string</span><span class="sxs-lookup"><span data-stu-id="555de-128">string</span></span> | <span data-ttu-id="555de-129">Nombre del Departamento al que pertenece el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="555de-130">string</span><span class="sxs-lookup"><span data-stu-id="555de-130">string</span></span> | <span data-ttu-id="555de-131">Puesto del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="555de-132">string</span><span class="sxs-lookup"><span data-stu-id="555de-132">string</span></span> | <span data-ttu-id="555de-133">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="555de-134">string</span><span class="sxs-lookup"><span data-stu-id="555de-134">string</span></span> | <span data-ttu-id="555de-135">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="555de-136">string</span><span class="sxs-lookup"><span data-stu-id="555de-136">string</span></span> | <span data-ttu-id="555de-137">Dirección SMTP de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="555de-138">string</span><span class="sxs-lookup"><span data-stu-id="555de-138">string</span></span> | <span data-ttu-id="555de-139">Voz de la dirección IP (VOIP) protocolo de inicio de sesión (SIP) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="555de-140">string</span><span class="sxs-lookup"><span data-stu-id="555de-140">string</span></span> | <span data-ttu-id="555de-141">Ciudad en la que se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="555de-142">string</span><span class="sxs-lookup"><span data-stu-id="555de-142">string</span></span> | <span data-ttu-id="555de-143">País o región donde se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="555de-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="555de-144">boolean</span><span class="sxs-lookup"><span data-stu-id="555de-144">boolean</span></span> | <span data-ttu-id="555de-145">Indica si la cuenta está habilitada o no.</span><span class="sxs-lookup"><span data-stu-id="555de-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="555de-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="555de-146">Related topics</span></span>
- [<span data-ttu-id="555de-147">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="555de-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="555de-148">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="555de-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="555de-149">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="555de-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="555de-150">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="555de-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="555de-151">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="555de-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="555de-152">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="555de-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
