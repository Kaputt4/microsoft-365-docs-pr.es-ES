---
title: Tabla IdentityDirectoryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de controlador de dominio y Active Directory en la tabla IdentityDirectoryEvents del esquema de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityDirectoryEvents, controlador de dominio, Active Directory, ATP de Azure, identidades
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 41b429e32122d6cc58a746649c8a0428f0a90b0f
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847433"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="77edc-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="77edc-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="77edc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="77edc-105">**Applies to:**</span></span>
- <span data-ttu-id="77edc-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="77edc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="77edc-107">La `IdentityDirectoryEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene eventos que implican un controlador de dominio local que ejecuta Active Directory (ad).</span><span class="sxs-lookup"><span data-stu-id="77edc-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="77edc-108">Esta tabla captura varios eventos relacionados con la identidad, como cambios de contraseña, expiración de contraseñas y cambios de nombre principal de usuario (UPN).</span><span class="sxs-lookup"><span data-stu-id="77edc-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="77edc-109">También captura eventos del sistema en el controlador de dominio, como la programación de tareas y la actividad de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77edc-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="77edc-110">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="77edc-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="77edc-111">Para obtener información detallada acerca de los tipos de eventos ( `ActionType` valores) admitidos por una tabla, use la [referencia de esquema integrada](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponible en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="77edc-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="77edc-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="77edc-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="77edc-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="77edc-113">Column name</span></span> | <span data-ttu-id="77edc-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="77edc-114">Data type</span></span> | <span data-ttu-id="77edc-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="77edc-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="77edc-116">datetime</span><span class="sxs-lookup"><span data-stu-id="77edc-116">datetime</span></span> | <span data-ttu-id="77edc-117">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="77edc-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="77edc-118">cadena</span><span class="sxs-lookup"><span data-stu-id="77edc-118">string</span></span> | <span data-ttu-id="77edc-119">Tipo de actividad que ha desencadenado el evento.</span><span class="sxs-lookup"><span data-stu-id="77edc-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="77edc-120">Consulte la [Referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más detalles</span><span class="sxs-lookup"><span data-stu-id="77edc-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="77edc-121">string</span><span class="sxs-lookup"><span data-stu-id="77edc-121">string</span></span> | <span data-ttu-id="77edc-122">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="77edc-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="77edc-123">string</span><span class="sxs-lookup"><span data-stu-id="77edc-123">string</span></span> | <span data-ttu-id="77edc-124">Nombre principal de usuario (UPN) de la cuenta a la que se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="77edc-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="77edc-125">string</span><span class="sxs-lookup"><span data-stu-id="77edc-125">string</span></span> | <span data-ttu-id="77edc-126">Nombre para mostrar de la cuenta a la que se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="77edc-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="77edc-127">string</span><span class="sxs-lookup"><span data-stu-id="77edc-127">string</span></span> | <span data-ttu-id="77edc-128">Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="77edc-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="77edc-129">string</span><span class="sxs-lookup"><span data-stu-id="77edc-129">string</span></span> | <span data-ttu-id="77edc-130">Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="77edc-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="77edc-131">string</span><span class="sxs-lookup"><span data-stu-id="77edc-131">string</span></span> | <span data-ttu-id="77edc-132">Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="77edc-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="77edc-133">string</span><span class="sxs-lookup"><span data-stu-id="77edc-133">string</span></span> | <span data-ttu-id="77edc-134">Puerto de destino de la actividad</span><span class="sxs-lookup"><span data-stu-id="77edc-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="77edc-135">string</span><span class="sxs-lookup"><span data-stu-id="77edc-135">string</span></span> | <span data-ttu-id="77edc-136">Protocolo usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="77edc-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="77edc-137">string</span><span class="sxs-lookup"><span data-stu-id="77edc-137">string</span></span> | <span data-ttu-id="77edc-138">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="77edc-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="77edc-139">string</span><span class="sxs-lookup"><span data-stu-id="77edc-139">string</span></span> | <span data-ttu-id="77edc-140">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="77edc-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="77edc-141">string</span><span class="sxs-lookup"><span data-stu-id="77edc-141">string</span></span> | <span data-ttu-id="77edc-142">Nombre principal de usuario (UPN) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="77edc-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="77edc-143">string</span><span class="sxs-lookup"><span data-stu-id="77edc-143">string</span></span> | <span data-ttu-id="77edc-144">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="77edc-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="77edc-145">string</span><span class="sxs-lookup"><span data-stu-id="77edc-145">string</span></span> | <span data-ttu-id="77edc-146">Identificador único de la cuenta en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="77edc-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="77edc-147">string</span><span class="sxs-lookup"><span data-stu-id="77edc-147">string</span></span> | <span data-ttu-id="77edc-148">Nombre del usuario de la cuenta que se muestra en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="77edc-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="77edc-149">Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido.</span><span class="sxs-lookup"><span data-stu-id="77edc-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="77edc-150">string</span><span class="sxs-lookup"><span data-stu-id="77edc-150">string</span></span> | <span data-ttu-id="77edc-151">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="77edc-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="77edc-152">string</span><span class="sxs-lookup"><span data-stu-id="77edc-152">string</span></span> | <span data-ttu-id="77edc-153">Dirección IP asignada al dispositivo durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="77edc-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="77edc-154">string</span><span class="sxs-lookup"><span data-stu-id="77edc-154">string</span></span> | <span data-ttu-id="77edc-155">Puerto TCP usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="77edc-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="77edc-156">string</span><span class="sxs-lookup"><span data-stu-id="77edc-156">string</span></span> | <span data-ttu-id="77edc-157">Ciudad, país u otra ubicación geográfica asociada con el evento</span><span class="sxs-lookup"><span data-stu-id="77edc-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="77edc-158">string</span><span class="sxs-lookup"><span data-stu-id="77edc-158">string</span></span> | <span data-ttu-id="77edc-159">Proveedor de servicios de Internet asociado con la dirección IP</span><span class="sxs-lookup"><span data-stu-id="77edc-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="77edc-160">largo</span><span class="sxs-lookup"><span data-stu-id="77edc-160">long</span></span> | <span data-ttu-id="77edc-161">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="77edc-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="77edc-162">string</span><span class="sxs-lookup"><span data-stu-id="77edc-162">string</span></span> | <span data-ttu-id="77edc-163">Información adicional acerca de la entidad o el evento</span><span class="sxs-lookup"><span data-stu-id="77edc-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="77edc-164">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="77edc-164">Related topics</span></span>
- [<span data-ttu-id="77edc-165">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="77edc-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="77edc-166">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="77edc-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="77edc-167">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="77edc-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="77edc-168">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="77edc-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="77edc-169">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="77edc-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="77edc-170">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="77edc-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
