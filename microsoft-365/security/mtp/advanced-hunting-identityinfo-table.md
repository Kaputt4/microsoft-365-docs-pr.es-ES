---
title: Tabla IdentityInfo en el esquema de búsqueda avanzada
description: Información sobre la cuenta de usuario en la tabla IdentityInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AccountInfo, IdentityInfo, cuenta
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
ms.openlocfilehash: b384e76439ae706520725e7193fa64224b724be0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898962"
---
# <a name="identityinfo"></a><span data-ttu-id="ecbd6-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="ecbd6-104">IdentityInfo</span></span>

<span data-ttu-id="ecbd6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ecbd6-105">**Applies to:**</span></span>
- <span data-ttu-id="ecbd6-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ecbd6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ecbd6-107">La `IdentityInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las cuentas de usuario obtenidas de varios servicios, incluido Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ecbd6-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="ecbd6-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="ecbd6-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="ecbd6-109">Se cambió el nombre de esta tabla de `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="ecbd6-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="ecbd6-110">Durante el cambio de nombre, se actualizan automáticamente todas las consultas guardadas en el portal.</span><span class="sxs-lookup"><span data-stu-id="ecbd6-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="ecbd6-111">Compruebe las consultas que guardó en otra parte.</span><span class="sxs-lookup"><span data-stu-id="ecbd6-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="ecbd6-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ecbd6-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ecbd6-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="ecbd6-113">Column name</span></span> | <span data-ttu-id="ecbd6-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ecbd6-114">Data type</span></span> | <span data-ttu-id="ecbd6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecbd6-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="ecbd6-116">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-116">string</span></span> | <span data-ttu-id="ecbd6-117">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="ecbd6-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="ecbd6-118">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-118">string</span></span> | <span data-ttu-id="ecbd6-119">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="ecbd6-120">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-120">string</span></span> | <span data-ttu-id="ecbd6-121">Identificador de seguridad local (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="ecbd6-122">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-122">string</span></span> | <span data-ttu-id="ecbd6-123">Identificador de seguridad en la nube de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="ecbd6-124">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-124">string</span></span> | <span data-ttu-id="ecbd6-125">Nombre especificado o nombre del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="ecbd6-126">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-126">string</span></span> | <span data-ttu-id="ecbd6-127">Apellidos, apellidos o familia del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="ecbd6-128">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-128">string</span></span> | <span data-ttu-id="ecbd6-129">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="ecbd6-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="ecbd6-130">Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido.</span><span class="sxs-lookup"><span data-stu-id="ecbd6-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="ecbd6-131">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-131">string</span></span> | <span data-ttu-id="ecbd6-132">Nombre del Departamento al que pertenece el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="ecbd6-133">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-133">string</span></span> | <span data-ttu-id="ecbd6-134">Puesto del usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="ecbd6-135">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-135">string</span></span> | <span data-ttu-id="ecbd6-136">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="ecbd6-137">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-137">string</span></span> | <span data-ttu-id="ecbd6-138">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="ecbd6-139">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-139">string</span></span> | <span data-ttu-id="ecbd6-140">Dirección SMTP de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="ecbd6-141">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-141">string</span></span> | <span data-ttu-id="ecbd6-142">Voz de la dirección IP (VOIP) protocolo de inicio de sesión (SIP) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-142">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="ecbd6-143">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-143">string</span></span> | <span data-ttu-id="ecbd6-144">Ciudad en la que se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="ecbd6-145">string</span><span class="sxs-lookup"><span data-stu-id="ecbd6-145">string</span></span> | <span data-ttu-id="ecbd6-146">País o región donde se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="ecbd6-147">boolean</span><span class="sxs-lookup"><span data-stu-id="ecbd6-147">boolean</span></span> | <span data-ttu-id="ecbd6-148">Indica si la cuenta está habilitada o no.</span><span class="sxs-lookup"><span data-stu-id="ecbd6-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ecbd6-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ecbd6-149">Related topics</span></span>
- [<span data-ttu-id="ecbd6-150">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="ecbd6-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ecbd6-151">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ecbd6-152">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="ecbd6-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ecbd6-153">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="ecbd6-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ecbd6-154">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="ecbd6-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ecbd6-155">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="ecbd6-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
