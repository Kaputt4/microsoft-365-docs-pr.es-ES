---
title: Migrar consultas de búsqueda avanzada de Microsoft defender para el punto de conexión
description: Aprenda a ajustar las consultas de Microsoft defender para el punto de conexión para que pueda usarlas en Microsoft 365 defender
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, ATP de Microsoft defender, mdatp, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, Microsoft 365, asignación
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846861"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="0853e-104">Migrar consultas de búsqueda avanzada de Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0853e-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0853e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0853e-105">**Applies to:**</span></span>
- <span data-ttu-id="0853e-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="0853e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0853e-107">Mueva los flujos de trabajo de caza avanzados de Microsoft defender para el punto de conexión para buscar de forma proactiva las amenazas con un conjunto de datos más amplio.</span><span class="sxs-lookup"><span data-stu-id="0853e-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="0853e-108">En Microsoft 365 defender, obtiene acceso a datos de otras soluciones de seguridad de Microsoft 365, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="0853e-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="0853e-109">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0853e-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="0853e-110">Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0853e-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="0853e-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0853e-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="0853e-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0853e-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="0853e-113">La mayoría de los clientes de Microsoft defender para extremo pueden [usar microsoft 365 defender sin licencias adicionales](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="0853e-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="0853e-114">Para empezar a migrar los flujos de trabajo de caza avanzados de defender para el punto de conexión, [Active Microsoft 365 defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="0853e-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="0853e-115">Puede realizar la transición sin afectar a los flujos de trabajo de defender existentes para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0853e-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="0853e-116">Las consultas guardadas permanecen intactas y las reglas de detección personalizadas continúan ejecutándose y generando alertas.</span><span class="sxs-lookup"><span data-stu-id="0853e-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="0853e-117">Sin embargo, estarán visibles en Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="0853e-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="0853e-118">Tablas de esquema en Microsoft 365 defender solamente</span><span class="sxs-lookup"><span data-stu-id="0853e-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="0853e-119">El [esquema de búsqueda avanzada de microsoft 365 defender](advanced-hunting-schema-tables.md) proporciona tablas adicionales que contienen datos de diversas soluciones de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0853e-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="0853e-120">Las siguientes tablas solo están disponibles en Microsoft 365 defender:</span><span class="sxs-lookup"><span data-stu-id="0853e-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="0853e-121">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="0853e-121">Table name</span></span> | <span data-ttu-id="0853e-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="0853e-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="0853e-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="0853e-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="0853e-124">Archivos, direcciones IP, URL, usuarios o dispositivos asociados con alertas</span><span class="sxs-lookup"><span data-stu-id="0853e-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="0853e-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="0853e-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="0853e-126">Alertas de Microsoft defender para el punto de conexión, Microsoft defender para Office 365, Microsoft Cloud App Security y Microsoft defender para identidad, incluida la información de gravedad y las categorías de amenaza</span><span class="sxs-lookup"><span data-stu-id="0853e-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="0853e-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="0853e-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="0853e-128">Actividades relacionadas con archivos en aplicaciones y servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="0853e-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="0853e-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="0853e-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="0853e-130">Información sobre los archivos adjuntos a los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="0853e-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="0853e-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="0853e-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="0853e-132">Eventos de correo electrónico de Microsoft 365, incluidos eventos de bloqueo y entrega de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="0853e-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="0853e-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="0853e-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="0853e-134">Eventos de seguridad que se producen después de la entrega, después de que Microsoft 365 haya entregado los correos electrónicos al buzón del destinatario</span><span class="sxs-lookup"><span data-stu-id="0853e-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="0853e-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="0853e-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="0853e-136">Información sobre las direcciones URL en correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="0853e-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="0853e-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="0853e-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="0853e-138">Eventos que implican un controlador de dominio local que ejecuta Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="0853e-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="0853e-139">Esta tabla cubre una amplia variedad de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="0853e-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="0853e-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="0853e-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="0853e-141">Información de cuenta de varios orígenes, incluido Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0853e-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="0853e-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="0853e-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="0853e-143">Eventos de autenticación en Active Directory y Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="0853e-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="0853e-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="0853e-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="0853e-145">Consultas de objetos de Active Directory, como usuarios, grupos, dispositivos y dominios</span><span class="sxs-lookup"><span data-stu-id="0853e-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="0853e-146">Tabla DeviceAlertEvents de mapa</span><span class="sxs-lookup"><span data-stu-id="0853e-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="0853e-147">Las `AlertInfo` `AlertEvidence` tablas y reemplazan la `DeviceAlertEvents` tabla en el esquema de Microsoft defender para extremo.</span><span class="sxs-lookup"><span data-stu-id="0853e-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="0853e-148">Además de datos sobre alertas de dispositivos, estas dos tablas incluyen datos sobre las alertas de identidades, aplicaciones y mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0853e-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="0853e-149">Use la tabla siguiente para comprobar el modo en que `DeviceAlertEvents` las columnas se asignan a las columnas en las `AlertInfo` `AlertEvidence` tablas y.</span><span class="sxs-lookup"><span data-stu-id="0853e-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="0853e-150">Además de las columnas de la tabla siguiente, la `AlertEvidence` tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="0853e-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="0853e-151">Ver todas las columnas de AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="0853e-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="0853e-152">Columna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="0853e-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="0853e-153">Dónde encontrar los mismos datos en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="0853e-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="0853e-154">`AlertInfo``AlertEvidence`tablas y</span><span class="sxs-lookup"><span data-stu-id="0853e-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="0853e-155">`AlertInfo``AlertEvidence`tablas y</span><span class="sxs-lookup"><span data-stu-id="0853e-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="0853e-156">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="0853e-157">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="0853e-158">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="0853e-159">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="0853e-160">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="0853e-161">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="0853e-162">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="0853e-163">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="0853e-164">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="0853e-165">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="0853e-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="0853e-166">Esta columna se suele usar en Microsoft defender para Endpoint para buscar registros relacionados en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="0853e-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="0853e-167">En Microsoft 365 defender, puede obtener datos relacionados directamente de la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="0853e-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="0853e-168">Esta columna se suele usar en Microsoft defender para el punto de conexión para obtener información adicional sobre eventos en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="0853e-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="0853e-169">En Microsoft 365 defender, puede obtener datos relacionados directamente de la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="0853e-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="0853e-170">Ajustar las consultas existentes de Microsoft defender para Endpoint</span><span class="sxs-lookup"><span data-stu-id="0853e-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="0853e-171">Las consultas de Microsoft defender for Endpoint funcionarán tal cual, a menos que hagan referencia a la `DeviceAlertEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="0853e-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="0853e-172">Para usar estas consultas en Microsoft 365 defender, aplique estos cambios:</span><span class="sxs-lookup"><span data-stu-id="0853e-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="0853e-173">Reemplazar `DeviceAlertEvents` por `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="0853e-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="0853e-174">Una el `AlertInfo` y las `AlertEvidence` tablas en `AlertId` para obtener datos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="0853e-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="0853e-175">Consulta original</span><span class="sxs-lookup"><span data-stu-id="0853e-175">Original query</span></span>
<span data-ttu-id="0853e-176">La siguiente consulta usa `DeviceAlertEvents` en Microsoft defender para el punto de conexión para obtener las alertas que implican _powershell.exe_ :</span><span class="sxs-lookup"><span data-stu-id="0853e-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_ :</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="0853e-177">Consulta modificada</span><span class="sxs-lookup"><span data-stu-id="0853e-177">Modified query</span></span>
<span data-ttu-id="0853e-178">La siguiente consulta se ha ajustado para su uso en Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="0853e-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="0853e-179">En lugar de comprobar el nombre de archivo directamente desde `DeviceAlertEvents` , se unen `AlertEvidence` y se comprueba el nombre de archivo en esa tabla.</span><span class="sxs-lookup"><span data-stu-id="0853e-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="0853e-180">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0853e-180">Related topics</span></span>
- [<span data-ttu-id="0853e-181">Activar Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="0853e-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0853e-182">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="0853e-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0853e-183">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="0853e-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0853e-184">Búsqueda avanzada en Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0853e-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)