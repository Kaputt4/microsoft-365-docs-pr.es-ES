---
title: Tabla IdentityInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la cuenta de usuario en la tabla IdentityInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AccountInfo, IdentityInfo, cuenta
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
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935826"
---
# <a name="identityinfo"></a><span data-ttu-id="f531c-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="f531c-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f531c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f531c-105">**Applies to:**</span></span>
- <span data-ttu-id="f531c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f531c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f531c-107">La tabla del esquema de búsqueda avanzada contiene información sobre las cuentas de usuario obtenidas de varios `IdentityInfo` servicios, incluidos [](advanced-hunting-overview.md) Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f531c-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="f531c-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="f531c-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="f531c-109">Esta tabla cambió el nombre de `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="f531c-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="f531c-110">Durante los cambios de nombre, todas las consultas guardadas en el portal se actualizan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f531c-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="f531c-111">Comprueba las consultas que has guardado en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="f531c-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="f531c-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f531c-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f531c-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="f531c-113">Column name</span></span> | <span data-ttu-id="f531c-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f531c-114">Data type</span></span> | <span data-ttu-id="f531c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f531c-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="f531c-116">string</span><span class="sxs-lookup"><span data-stu-id="f531c-116">string</span></span> | <span data-ttu-id="f531c-117">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="f531c-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="f531c-118">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-118">string</span></span> | <span data-ttu-id="f531c-119">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="f531c-120">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-120">string</span></span> | <span data-ttu-id="f531c-121">Identificador de seguridad local (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="f531c-122">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-122">string</span></span> | <span data-ttu-id="f531c-123">Identificador de seguridad en la nube de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="f531c-124">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-124">string</span></span> | <span data-ttu-id="f531c-125">Nombre o nombre del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="f531c-126">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-126">string</span></span> | <span data-ttu-id="f531c-127">Apellidos, apellidos o apellidos del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f531c-128">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-128">string</span></span> | <span data-ttu-id="f531c-129">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="f531c-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f531c-130">Normalmente, una combinación de un nombre o un nombre determinado, un inicio intermedio y un apellido o apellido.</span><span class="sxs-lookup"><span data-stu-id="f531c-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="f531c-131">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-131">string</span></span> | <span data-ttu-id="f531c-132">Nombre del departamento al que pertenece el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="f531c-133">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-133">string</span></span> | <span data-ttu-id="f531c-134">Título del trabajo del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="f531c-135">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-135">string</span></span> | <span data-ttu-id="f531c-136">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f531c-137">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-137">string</span></span> | <span data-ttu-id="f531c-138">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="f531c-139">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-139">string</span></span> | <span data-ttu-id="f531c-140">Dirección SMTP de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="f531c-141">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-141">string</span></span> | <span data-ttu-id="f531c-142">Dirección del protocolo de inicio de sesión (SIP) de voz sobre IP (VOIP) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="f531c-143">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-143">string</span></span> | <span data-ttu-id="f531c-144">Ciudad donde se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="f531c-145">cadena</span><span class="sxs-lookup"><span data-stu-id="f531c-145">string</span></span> | <span data-ttu-id="f531c-146">País o región donde se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="f531c-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="f531c-147">boolean</span><span class="sxs-lookup"><span data-stu-id="f531c-147">boolean</span></span> | <span data-ttu-id="f531c-148">Indica si la cuenta está habilitada o no</span><span class="sxs-lookup"><span data-stu-id="f531c-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f531c-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f531c-149">Related topics</span></span>
- [<span data-ttu-id="f531c-150">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="f531c-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f531c-151">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="f531c-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f531c-152">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="f531c-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f531c-153">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="f531c-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f531c-154">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="f531c-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f531c-155">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="f531c-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
