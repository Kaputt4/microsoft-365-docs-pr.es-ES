---
title: Tabla IdentityDirectoryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre el controlador de dominio y los eventos de Active Directory en la tabla IdentityDirectoryEvents del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityDirectoryEvents, controlador de dominio, Active Directory, ATP de Azure, identidades
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
ms.openlocfilehash: 73018bb65c011d10234ec9c02fc61bfb93fa125a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501127"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="2ef4d-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="2ef4d-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2ef4d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2ef4d-105">**Applies to:**</span></span>
- <span data-ttu-id="2ef4d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ef4d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2ef4d-107">La tabla del esquema de búsqueda avanzada contiene eventos que implican un controlador de `IdentityDirectoryEvents` dominio local que ejecuta Active Directory (AD). [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2ef4d-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="2ef4d-108">Esta tabla captura varios eventos relacionados con la identidad, como cambios de contraseña, expiración de contraseña y cambios de nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="2ef4d-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="2ef4d-109">También captura eventos del sistema en el controlador de dominio, como la programación de tareas y la actividad de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ef4d-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="2ef4d-110">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ef4d-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="2ef4d-111">Para obtener información detallada acerca de los tipos de eventos ( valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2ef4d-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="2ef4d-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2ef4d-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2ef4d-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="2ef4d-113">Column name</span></span> | <span data-ttu-id="2ef4d-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2ef4d-114">Data type</span></span> | <span data-ttu-id="2ef4d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ef4d-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2ef4d-116">datetime</span><span class="sxs-lookup"><span data-stu-id="2ef4d-116">datetime</span></span> | <span data-ttu-id="2ef4d-117">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="2ef4d-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="2ef4d-118">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-118">string</span></span> | <span data-ttu-id="2ef4d-119">Tipo de actividad que desencadenó el evento.</span><span class="sxs-lookup"><span data-stu-id="2ef4d-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="2ef4d-120">Vea la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información</span><span class="sxs-lookup"><span data-stu-id="2ef4d-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="2ef4d-121">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-121">string</span></span> | <span data-ttu-id="2ef4d-122">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="2ef4d-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="2ef4d-123">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-123">string</span></span> | <span data-ttu-id="2ef4d-124">Nombre principal de usuario (UPN) de la cuenta a la que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="2ef4d-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="2ef4d-125">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-125">string</span></span> | <span data-ttu-id="2ef4d-126">Nombre para mostrar de la cuenta a la que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="2ef4d-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="2ef4d-127">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-127">string</span></span> | <span data-ttu-id="2ef4d-128">Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="2ef4d-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="2ef4d-129">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-129">string</span></span> | <span data-ttu-id="2ef4d-130">Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="2ef4d-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="2ef4d-131">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-131">string</span></span> | <span data-ttu-id="2ef4d-132">Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="2ef4d-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="2ef4d-133">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-133">string</span></span> | <span data-ttu-id="2ef4d-134">Puerto de destino de la actividad</span><span class="sxs-lookup"><span data-stu-id="2ef4d-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="2ef4d-135">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-135">string</span></span> | <span data-ttu-id="2ef4d-136">Protocolo usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="2ef4d-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="2ef4d-137">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-137">string</span></span> | <span data-ttu-id="2ef4d-138">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="2ef4d-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="2ef4d-139">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-139">string</span></span> | <span data-ttu-id="2ef4d-140">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="2ef4d-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="2ef4d-141">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-141">string</span></span> | <span data-ttu-id="2ef4d-142">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="2ef4d-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="2ef4d-143">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-143">string</span></span> | <span data-ttu-id="2ef4d-144">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="2ef4d-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="2ef4d-145">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-145">string</span></span> | <span data-ttu-id="2ef4d-146">Identificador único de la cuenta en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2ef4d-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2ef4d-147">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-147">string</span></span> | <span data-ttu-id="2ef4d-148">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="2ef4d-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2ef4d-149">Normalmente, una combinación de un nombre o un nombre determinado, un inicio intermedio y un apellido o apellido.</span><span class="sxs-lookup"><span data-stu-id="2ef4d-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="2ef4d-150">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-150">string</span></span> | <span data-ttu-id="2ef4d-151">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2ef4d-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="2ef4d-152">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-152">string</span></span> | <span data-ttu-id="2ef4d-153">Dirección IP asignada al dispositivo durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="2ef4d-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="2ef4d-154">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-154">string</span></span> | <span data-ttu-id="2ef4d-155">Puerto TCP usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="2ef4d-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="2ef4d-156">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-156">string</span></span> | <span data-ttu-id="2ef4d-157">Ciudad, país u otra ubicación geográfica asociada al evento</span><span class="sxs-lookup"><span data-stu-id="2ef4d-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="2ef4d-158">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-158">string</span></span> | <span data-ttu-id="2ef4d-159">Proveedor de servicios de Internet asociado con la dirección IP</span><span class="sxs-lookup"><span data-stu-id="2ef4d-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="2ef4d-160">largo</span><span class="sxs-lookup"><span data-stu-id="2ef4d-160">long</span></span> | <span data-ttu-id="2ef4d-161">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="2ef4d-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="2ef4d-162">cadena</span><span class="sxs-lookup"><span data-stu-id="2ef4d-162">string</span></span> | <span data-ttu-id="2ef4d-163">Información adicional sobre la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="2ef4d-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2ef4d-164">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2ef4d-164">Related topics</span></span>
- [<span data-ttu-id="2ef4d-165">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="2ef4d-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2ef4d-166">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="2ef4d-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2ef4d-167">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="2ef4d-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2ef4d-168">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="2ef4d-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2ef4d-169">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="2ef4d-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2ef4d-170">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="2ef4d-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
