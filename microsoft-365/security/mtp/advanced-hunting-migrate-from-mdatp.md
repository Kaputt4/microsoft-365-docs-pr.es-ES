---
title: Migrar consultas de búsqueda avanzada de Microsoft Defender para endpoint
description: Obtenga información sobre cómo ajustar Microsoft Defender para las consultas de puntos de conexión para que pueda usarlas en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, atp de microsoft defender, mdatp, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, microsoft 365, asignación
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094812"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="04467-104">Migrar consultas de búsqueda avanzada de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="04467-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="04467-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="04467-105">**Applies to:**</span></span>
- <span data-ttu-id="04467-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04467-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="04467-107">Mueva los flujos de trabajo de búsqueda avanzada de Microsoft Defender for Endpoint para buscar de forma proactiva amenazas mediante un conjunto más amplio de datos.</span><span class="sxs-lookup"><span data-stu-id="04467-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="04467-108">En Microsoft 365 Defender, obtiene acceso a los datos de otras soluciones de seguridad de Microsoft 365, como:</span><span class="sxs-lookup"><span data-stu-id="04467-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="04467-109">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="04467-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="04467-110">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="04467-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="04467-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="04467-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="04467-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="04467-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="04467-113">La mayoría de los clientes de Microsoft Defender para puntos de conexión [pueden usar Microsoft 365 Defender sin licencias adicionales.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="04467-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="04467-114">Para empezar a realizar la transición de los flujos de trabajo de búsqueda avanzada desde Defender para endpoint, [active Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="04467-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="04467-115">Puede realizar la transición sin afectar a los flujos de trabajo existentes de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="04467-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="04467-116">Las consultas guardadas permanecen intactas y las reglas de detección personalizadas siguen funcionando y generando alertas.</span><span class="sxs-lookup"><span data-stu-id="04467-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="04467-117">Sin embargo, estarán visibles en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="04467-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="04467-118">Tablas de esquema solo en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04467-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="04467-119">El esquema de búsqueda avanzada [de Microsoft 365 Defender](advanced-hunting-schema-tables.md) proporciona tablas adicionales que contienen datos de varias soluciones de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04467-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="04467-120">Las tablas siguientes solo están disponibles en Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="04467-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="04467-121">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="04467-121">Table name</span></span> | <span data-ttu-id="04467-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="04467-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="04467-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="04467-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="04467-124">Archivos, direcciones IP, direcciones URL, usuarios o dispositivos asociados con alertas</span><span class="sxs-lookup"><span data-stu-id="04467-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="04467-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="04467-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="04467-126">Alertas de Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identity, incluidas la información de gravedad y las categorías de amenazas</span><span class="sxs-lookup"><span data-stu-id="04467-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="04467-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="04467-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="04467-128">Actividades relacionadas con archivos en servicios y aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="04467-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="04467-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="04467-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="04467-130">Información sobre los archivos adjuntos a los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="04467-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="04467-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="04467-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="04467-132">Eventos de correo electrónico de Microsoft 365, incluidos los eventos de entrega y bloqueo de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="04467-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="04467-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="04467-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="04467-134">Eventos de seguridad que se producen después de la entrega, después de que Microsoft 365 haya entregado los correos electrónicos al buzón del destinatario</span><span class="sxs-lookup"><span data-stu-id="04467-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="04467-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="04467-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="04467-136">Información sobre las direcciones URL de los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="04467-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="04467-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="04467-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="04467-138">Eventos que implican a un controlador de dominio local que ejecuta Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="04467-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="04467-139">En esta tabla se trata una serie de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="04467-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="04467-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="04467-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="04467-141">Información de cuenta de varios orígenes, incluido Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="04467-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="04467-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="04467-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="04467-143">Eventos de autenticación en Active Directory y servicios en línea de Microsoft</span><span class="sxs-lookup"><span data-stu-id="04467-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="04467-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="04467-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="04467-145">Consultas de objetos de Active Directory, como usuarios, grupos, dispositivos y dominios</span><span class="sxs-lookup"><span data-stu-id="04467-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="04467-146">Asignar tabla DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="04467-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="04467-147">Las `AlertInfo` tablas y `AlertEvidence` reemplazan la tabla en el esquema de `DeviceAlertEvents` Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="04467-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="04467-148">Además de los datos sobre las alertas de dispositivo, estas dos tablas incluyen datos sobre alertas de identidades, aplicaciones y correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="04467-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="04467-149">Use la tabla siguiente para comprobar cómo se asignan `DeviceAlertEvents` las columnas a las columnas de las tablas `AlertInfo` `AlertEvidence` y.</span><span class="sxs-lookup"><span data-stu-id="04467-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="04467-150">Además de las columnas de la tabla siguiente, la tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas `AlertEvidence` de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="04467-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="04467-151">Ver todas las columnas AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="04467-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="04467-152">Columna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="04467-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="04467-153">Dónde encontrar los mismos datos en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04467-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="04467-154">`AlertInfo` y  `AlertEvidence` tablas</span><span class="sxs-lookup"><span data-stu-id="04467-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="04467-155">`AlertInfo` y  `AlertEvidence` tablas</span><span class="sxs-lookup"><span data-stu-id="04467-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="04467-156">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="04467-157">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="04467-158">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="04467-159">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="04467-160">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="04467-161">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="04467-162">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="04467-163">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="04467-164">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="04467-165">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="04467-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="04467-166">Esta columna se usa normalmente en Microsoft Defender para Endpoint para buscar registros relacionados en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="04467-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="04467-167">En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="04467-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="04467-168">Esta columna se usa normalmente en Microsoft Defender para Endpoint para obtener información adicional sobre eventos en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="04467-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="04467-169">En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="04467-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="04467-170">Ajustar Las consultas existentes de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="04467-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="04467-171">Las consultas de Microsoft Defender para puntos de conexión funcionarán tal y como están a menos que hacen referencia a la `DeviceAlertEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="04467-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="04467-172">Para usar estas consultas en Microsoft 365 Defender, aplique estos cambios:</span><span class="sxs-lookup"><span data-stu-id="04467-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="04467-173">Reemplazar `DeviceAlertEvents` por `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="04467-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="04467-174">Una las `AlertInfo` tablas y las tablas para obtener datos `AlertEvidence` `AlertId` equivalentes.</span><span class="sxs-lookup"><span data-stu-id="04467-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="04467-175">Consulta original</span><span class="sxs-lookup"><span data-stu-id="04467-175">Original query</span></span>
<span data-ttu-id="04467-176">La siguiente consulta usa `DeviceAlertEvents` Microsoft Defender para Endpoint para obtener las alertas que _implicanpowershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="04467-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="04467-177">Consulta modificada</span><span class="sxs-lookup"><span data-stu-id="04467-177">Modified query</span></span>
<span data-ttu-id="04467-178">Se ha ajustado la consulta siguiente para su uso en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="04467-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="04467-179">En lugar de comprobar el nombre de archivo directamente desde , se une y `DeviceAlertEvents` comprueba el nombre de archivo en esa `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="04467-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a><span data-ttu-id="04467-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04467-180">See also</span></span>
- [<span data-ttu-id="04467-181">Activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04467-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="04467-182">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="04467-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="04467-183">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="04467-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="04467-184">Búsqueda avanzada en Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="04467-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)