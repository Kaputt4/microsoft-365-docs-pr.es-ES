---
title: Migrar consultas de búsqueda avanzada desde ATP de Microsoft defender
description: Obtenga información sobre cómo ajustar las consultas de ATP de Microsoft defender para que pueda usarlas en la protección contra amenazas de Microsoft
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
ms.openlocfilehash: f56360b28a9fe9de4198d97954a64a429d1d99a5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429700"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="f2ebf-104">Migrar consultas de búsqueda avanzada desde ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="f2ebf-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f2ebf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f2ebf-105">**Applies to:**</span></span>
- <span data-ttu-id="f2ebf-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2ebf-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f2ebf-107">Mueva sus flujos de trabajo de caza avanzados de Microsoft defender ATP para buscar de forma proactiva las amenazas con un conjunto de datos más amplio.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="f2ebf-108">En Microsoft Threat Protection, obtiene acceso a datos de otras soluciones de seguridad de Microsoft 365, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="f2ebf-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="f2ebf-109">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f2ebf-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="f2ebf-110">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="f2ebf-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="f2ebf-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f2ebf-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f2ebf-112">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f2ebf-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="f2ebf-113">La mayoría de los clientes ATP de Microsoft defender pueden [usar la protección contra amenazas de Microsoft sin licencias adicionales](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="f2ebf-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="f2ebf-114">Para empezar a realizar la transición de los flujos de trabajo de búsqueda avanzada de ATP de Microsoft defender, [Active la protección contra amenazas de Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="f2ebf-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="f2ebf-115">Puede realizar la transición sin afectar a los flujos de trabajo de ATP existentes de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="f2ebf-116">Las consultas guardadas permanecen intactas y las reglas de detección personalizadas continúan ejecutándose y generando alertas.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="f2ebf-117">Sin embargo, estarán visibles en la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="f2ebf-118">Tablas de esquema de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2ebf-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="f2ebf-119">El [esquema de búsqueda avanzada de Microsoft Threat Protection](advanced-hunting-schema-tables.md) proporciona tablas adicionales que contienen datos de diversas soluciones de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="f2ebf-120">Las siguientes tablas solo están disponibles en protección contra amenazas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="f2ebf-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="f2ebf-121">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="f2ebf-121">Table name</span></span> | <span data-ttu-id="f2ebf-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2ebf-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="f2ebf-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="f2ebf-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="f2ebf-124">Archivos, direcciones IP, URL, usuarios o dispositivos asociados con alertas</span><span class="sxs-lookup"><span data-stu-id="f2ebf-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="f2ebf-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="f2ebf-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="f2ebf-126">Alertas de Microsoft defender ATP, Office 365 ATP, Microsoft Cloud App Security y Azure ATP, incluida la información de gravedad y las categorías de amenaza</span><span class="sxs-lookup"><span data-stu-id="f2ebf-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="f2ebf-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="f2ebf-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="f2ebf-128">Actividades relacionadas con archivos en aplicaciones y servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="f2ebf-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="f2ebf-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="f2ebf-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="f2ebf-130">Información sobre los archivos adjuntos a los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="f2ebf-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="f2ebf-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="f2ebf-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="f2ebf-132">Eventos de correo electrónico de Microsoft 365, incluidos eventos de bloqueo y entrega de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f2ebf-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="f2ebf-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="f2ebf-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="f2ebf-134">Eventos de seguridad que se producen después de la entrega, después de que Microsoft 365 haya entregado los correos electrónicos al buzón del destinatario</span><span class="sxs-lookup"><span data-stu-id="f2ebf-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="f2ebf-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="f2ebf-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="f2ebf-136">Información sobre las direcciones URL en correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="f2ebf-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="f2ebf-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="f2ebf-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="f2ebf-138">Eventos que implican un controlador de dominio local que ejecuta Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="f2ebf-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="f2ebf-139">Esta tabla cubre una amplia variedad de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="f2ebf-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="f2ebf-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="f2ebf-141">Información de cuenta de varios orígenes, incluido Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f2ebf-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="f2ebf-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="f2ebf-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="f2ebf-143">Eventos de autenticación en Active Directory y Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="f2ebf-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="f2ebf-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="f2ebf-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="f2ebf-145">Consultas de objetos de Active Directory, como usuarios, grupos, dispositivos y dominios</span><span class="sxs-lookup"><span data-stu-id="f2ebf-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="f2ebf-146">Tabla DeviceAlertEvents de mapa</span><span class="sxs-lookup"><span data-stu-id="f2ebf-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="f2ebf-147">Las `AlertInfo` `AlertEvidence` tablas y reemplazan la `DeviceAlertEvents` tabla en el esquema ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="f2ebf-148">Además de datos sobre alertas de dispositivos, estas dos tablas incluyen datos sobre las alertas de identidades, aplicaciones y mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="f2ebf-149">Use la tabla siguiente para comprobar el modo en que `DeviceAlertEvents` las columnas se asignan a las columnas en las `AlertInfo` `AlertEvidence` tablas y.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="f2ebf-150">Además de las columnas de la tabla siguiente, la `AlertEvidence` tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="f2ebf-151">Ver todas las columnas de AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="f2ebf-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="f2ebf-152">Columna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="f2ebf-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="f2ebf-153">Dónde encontrar los mismos datos en la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2ebf-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="f2ebf-154">`AlertInfo``AlertEvidence`tablas y</span><span class="sxs-lookup"><span data-stu-id="f2ebf-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="f2ebf-155">`AlertInfo``AlertEvidence`tablas y</span><span class="sxs-lookup"><span data-stu-id="f2ebf-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="f2ebf-156">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="f2ebf-157">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="f2ebf-158">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="f2ebf-159">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="f2ebf-160">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="f2ebf-161">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="f2ebf-162">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="f2ebf-163">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="f2ebf-164">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="f2ebf-165">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="f2ebf-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="f2ebf-166">Esta columna se suele usar en ATP de Microsoft defender para buscar registros relacionados en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="f2ebf-167">En la protección contra amenazas de Microsoft, puede obtener datos relacionados directamente de la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="f2ebf-168">Esta columna se suele usar en ATP de Microsoft defender para obtener información adicional sobre eventos en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="f2ebf-169">En la protección contra amenazas de Microsoft, puede obtener datos relacionados directamente de la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="f2ebf-170">Ajustar las consultas existentes de ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="f2ebf-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="f2ebf-171">Las consultas ATP de Microsoft defender funcionarán tal cual, a menos que hagan referencia a la `DeviceAlertEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="f2ebf-172">Para usar estas consultas en la protección contra amenazas de Microsoft, aplique estos cambios:</span><span class="sxs-lookup"><span data-stu-id="f2ebf-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="f2ebf-173">Reemplazar `DeviceAlertEvents` por `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="f2ebf-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="f2ebf-174">Una el `AlertInfo` y las `AlertEvidence` tablas en `AlertId` para obtener datos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="f2ebf-175">Consulta original</span><span class="sxs-lookup"><span data-stu-id="f2ebf-175">Original query</span></span>
<span data-ttu-id="f2ebf-176">La siguiente consulta usa `DeviceAlertEvents` ATP de Microsoft defender para obtener las alertas que implican _powershell.exe_:</span><span class="sxs-lookup"><span data-stu-id="f2ebf-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="f2ebf-177">Consulta modificada</span><span class="sxs-lookup"><span data-stu-id="f2ebf-177">Modified query</span></span>
<span data-ttu-id="f2ebf-178">La siguiente consulta se ha ajustado para su uso en Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="f2ebf-179">En lugar de comprobar el nombre de archivo directamente desde `DeviceAlertEvents` , se unen `AlertEvidence` y se comprueba el nombre de archivo en esa tabla.</span><span class="sxs-lookup"><span data-stu-id="f2ebf-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="f2ebf-180">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f2ebf-180">Related topics</span></span>
- [<span data-ttu-id="f2ebf-181">Habilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2ebf-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f2ebf-182">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="f2ebf-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f2ebf-183">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="f2ebf-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f2ebf-184">Búsqueda avanzada en ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="f2ebf-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)