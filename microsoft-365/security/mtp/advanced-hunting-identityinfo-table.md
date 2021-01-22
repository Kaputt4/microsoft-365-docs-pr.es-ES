---
title: Tabla IdentityInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la cuenta de usuario en la tabla IdentityInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AccountInfo, IdentityInfo, cuenta
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929915"
---
# <a name="identityinfo"></a><span data-ttu-id="9963a-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="9963a-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9963a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9963a-105">**Applies to:**</span></span>
- <span data-ttu-id="9963a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9963a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9963a-107">La tabla del esquema de búsqueda avanzada contiene información sobre las cuentas de usuario obtenidas de varios `IdentityInfo` servicios, incluido Azure Active Directory. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9963a-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="9963a-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="9963a-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="9963a-109">A esta tabla se le cambió el nombre `AccountInfo` de .</span><span class="sxs-lookup"><span data-stu-id="9963a-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="9963a-110">Durante los cambios de nombre, todas las consultas guardadas en el portal se actualizan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9963a-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="9963a-111">Compruebe las consultas que ha guardado en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="9963a-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="9963a-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9963a-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9963a-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="9963a-113">Column name</span></span> | <span data-ttu-id="9963a-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9963a-114">Data type</span></span> | <span data-ttu-id="9963a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9963a-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="9963a-116">string</span><span class="sxs-lookup"><span data-stu-id="9963a-116">string</span></span> | <span data-ttu-id="9963a-117">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="9963a-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="9963a-118">string</span><span class="sxs-lookup"><span data-stu-id="9963a-118">string</span></span> | <span data-ttu-id="9963a-119">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="9963a-120">string</span><span class="sxs-lookup"><span data-stu-id="9963a-120">string</span></span> | <span data-ttu-id="9963a-121">Identificador de seguridad local (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="9963a-122">string</span><span class="sxs-lookup"><span data-stu-id="9963a-122">string</span></span> | <span data-ttu-id="9963a-123">Identificador de seguridad en la nube de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="9963a-124">string</span><span class="sxs-lookup"><span data-stu-id="9963a-124">string</span></span> | <span data-ttu-id="9963a-125">Nombre o nombre del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="9963a-126">string</span><span class="sxs-lookup"><span data-stu-id="9963a-126">string</span></span> | <span data-ttu-id="9963a-127">Apellidos, apellidos o apellidos del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9963a-128">string</span><span class="sxs-lookup"><span data-stu-id="9963a-128">string</span></span> | <span data-ttu-id="9963a-129">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="9963a-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9963a-130">Normalmente, una combinación de un nombre o nombre, una iniciación intermedia y un apellido o apellido.</span><span class="sxs-lookup"><span data-stu-id="9963a-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="9963a-131">string</span><span class="sxs-lookup"><span data-stu-id="9963a-131">string</span></span> | <span data-ttu-id="9963a-132">Nombre del departamento al que pertenece el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="9963a-133">string</span><span class="sxs-lookup"><span data-stu-id="9963a-133">string</span></span> | <span data-ttu-id="9963a-134">Puesto del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="9963a-135">string</span><span class="sxs-lookup"><span data-stu-id="9963a-135">string</span></span> | <span data-ttu-id="9963a-136">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9963a-137">string</span><span class="sxs-lookup"><span data-stu-id="9963a-137">string</span></span> | <span data-ttu-id="9963a-138">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="9963a-139">string</span><span class="sxs-lookup"><span data-stu-id="9963a-139">string</span></span> | <span data-ttu-id="9963a-140">Dirección SMTP de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="9963a-141">string</span><span class="sxs-lookup"><span data-stu-id="9963a-141">string</span></span> | <span data-ttu-id="9963a-142">Dirección del protocolo de inicio de sesión (SIP) de voz sobre IP (VOIP) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="9963a-143">string</span><span class="sxs-lookup"><span data-stu-id="9963a-143">string</span></span> | <span data-ttu-id="9963a-144">Ciudad donde se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="9963a-145">string</span><span class="sxs-lookup"><span data-stu-id="9963a-145">string</span></span> | <span data-ttu-id="9963a-146">País o región donde se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9963a-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="9963a-147">boolean</span><span class="sxs-lookup"><span data-stu-id="9963a-147">boolean</span></span> | <span data-ttu-id="9963a-148">Indica si la cuenta está habilitada o no</span><span class="sxs-lookup"><span data-stu-id="9963a-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9963a-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9963a-149">Related topics</span></span>
- [<span data-ttu-id="9963a-150">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="9963a-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9963a-151">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="9963a-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9963a-152">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="9963a-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9963a-153">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="9963a-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9963a-154">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="9963a-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9963a-155">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="9963a-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
