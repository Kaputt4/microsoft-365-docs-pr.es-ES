---
title: Migrar consultas de búsqueda avanzada desde Microsoft Defender para endpoint
description: Obtenga información sobre cómo ajustar las consultas de Microsoft Defender para puntos de conexión para que pueda usarlas en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, Microsoft Defender para endpoint, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, asignación
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470693"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="82d5f-104">Migrar consultas de búsqueda avanzada desde Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="82d5f-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="82d5f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="82d5f-105">**Applies to:**</span></span>
- <span data-ttu-id="82d5f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82d5f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="82d5f-107">Mueva los flujos de trabajo de búsqueda avanzados de Microsoft Defender para endpoint para buscar de forma proactiva amenazas mediante un conjunto más amplio de datos.</span><span class="sxs-lookup"><span data-stu-id="82d5f-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="82d5f-108">En Microsoft 365 Defender, obtiene acceso a los datos de otras Microsoft 365 de seguridad, como:</span><span class="sxs-lookup"><span data-stu-id="82d5f-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="82d5f-109">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="82d5f-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="82d5f-110">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="82d5f-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="82d5f-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="82d5f-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="82d5f-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="82d5f-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="82d5f-113">La mayoría de los clientes de Microsoft Defender para [endpoints pueden usar Microsoft 365 Defender sin licencias adicionales.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="82d5f-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="82d5f-114">Para iniciar la transición de los flujos de trabajo de búsqueda avanzados desde Defender para endpoint, [active Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="82d5f-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="82d5f-115">Puede realizar la transición sin afectar a los flujos de trabajo existentes de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="82d5f-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="82d5f-116">Las consultas guardadas permanecen intactas y las reglas de detección personalizadas siguen funcionando y generando alertas.</span><span class="sxs-lookup"><span data-stu-id="82d5f-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="82d5f-117">Sin embargo, estarán visibles en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="82d5f-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="82d5f-118">Tablas de esquema solo Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82d5f-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="82d5f-119">El [Microsoft 365 de búsqueda](advanced-hunting-schema-tables.md) avanzada de Defender proporciona tablas adicionales que contienen datos de varias Microsoft 365 de seguridad.</span><span class="sxs-lookup"><span data-stu-id="82d5f-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="82d5f-120">Las tablas siguientes solo están disponibles en Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="82d5f-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="82d5f-121">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-121">Table name</span></span> | <span data-ttu-id="82d5f-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="82d5f-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="82d5f-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="82d5f-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="82d5f-124">Archivos, direcciones IP, direcciones URL, usuarios o dispositivos asociados con alertas</span><span class="sxs-lookup"><span data-stu-id="82d5f-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="82d5f-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="82d5f-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="82d5f-126">Alertas de Microsoft Defender para endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identidad, incluida la información de gravedad y las categorías de amenazas</span><span class="sxs-lookup"><span data-stu-id="82d5f-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="82d5f-127">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="82d5f-127">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="82d5f-128">Información sobre los archivos adjuntos a los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="82d5f-128">Information about files attached to emails</span></span> |
| [<span data-ttu-id="82d5f-129">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="82d5f-129">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="82d5f-130">Microsoft 365 de correo electrónico, incluidos los eventos de entrega y bloqueo de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="82d5f-130">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="82d5f-131">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="82d5f-131">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="82d5f-132">Eventos de seguridad que se producen después de la entrega, Microsoft 365 ha entregado los correos electrónicos al buzón de destinatario</span><span class="sxs-lookup"><span data-stu-id="82d5f-132">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="82d5f-133">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="82d5f-133">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="82d5f-134">Información sobre las direcciones URL de los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="82d5f-134">Information about URLs on emails</span></span> |
| [<span data-ttu-id="82d5f-135">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="82d5f-135">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="82d5f-136">Eventos que implican un controlador de dominio local que ejecuta Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="82d5f-136">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="82d5f-137">En esta tabla se describe un rango de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="82d5f-137">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="82d5f-138">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="82d5f-138">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="82d5f-139">Información de cuenta de varios orígenes, incluidos Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="82d5f-139">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="82d5f-140">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="82d5f-140">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="82d5f-141">Eventos de autenticación en Active Directory y servicios en línea de Microsoft</span><span class="sxs-lookup"><span data-stu-id="82d5f-141">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="82d5f-142">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="82d5f-142">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="82d5f-143">Consultas para objetos de Active Directory, como usuarios, grupos, dispositivos y dominios</span><span class="sxs-lookup"><span data-stu-id="82d5f-143">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="82d5f-144">Las consultas y detecciones personalizadas que usan tablas de esquema que solo están disponibles en Microsoft 365 Defender solo se pueden ver en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="82d5f-144">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="82d5f-145">Tabla Map DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="82d5f-145">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="82d5f-146">Las `AlertInfo` tablas y `AlertEvidence` reemplazan la tabla en el esquema de Microsoft `DeviceAlertEvents` Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="82d5f-146">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="82d5f-147">Además de los datos sobre alertas de dispositivos, estas dos tablas incluyen datos sobre alertas para identidades, aplicaciones y correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="82d5f-147">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="82d5f-148">Use la tabla siguiente para comprobar cómo se asignan `DeviceAlertEvents` las columnas a las columnas de las tablas `AlertInfo` `AlertEvidence` y.</span><span class="sxs-lookup"><span data-stu-id="82d5f-148">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="82d5f-149">Además de las columnas de la tabla siguiente, la tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas `AlertEvidence` de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="82d5f-149">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="82d5f-150">Ver todas las columnas alertevidence</span><span class="sxs-lookup"><span data-stu-id="82d5f-150">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="82d5f-151">Columna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="82d5f-151">DeviceAlertEvents column</span></span> | <span data-ttu-id="82d5f-152">Dónde encontrar los mismos datos en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82d5f-152">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="82d5f-153">`AlertInfo` y  `AlertEvidence` tablas</span><span class="sxs-lookup"><span data-stu-id="82d5f-153">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="82d5f-154">`AlertInfo` y  `AlertEvidence` tablas</span><span class="sxs-lookup"><span data-stu-id="82d5f-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="82d5f-155">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-155">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="82d5f-156">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-156">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="82d5f-157">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-157">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="82d5f-158">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-158">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="82d5f-159">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-159">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="82d5f-160">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-160">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="82d5f-161">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-161">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="82d5f-162">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-162">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="82d5f-163">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-163">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="82d5f-164">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="82d5f-164">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="82d5f-165">Esta columna se suele usar en Microsoft Defender para endpoint para buscar registros relacionados en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="82d5f-165">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="82d5f-166">En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="82d5f-166">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="82d5f-167">Esta columna se suele usar en Microsoft Defender para Endpoint para obtener información adicional sobre eventos en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="82d5f-167">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="82d5f-168">En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="82d5f-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="82d5f-169">Ajustar las consultas existentes de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="82d5f-169">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="82d5f-170">Las consultas de Microsoft Defender para puntos de conexión funcionarán tal como están a menos que haga referencia a la `DeviceAlertEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="82d5f-170">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="82d5f-171">Para usar estas consultas en Microsoft 365 Defender, aplique estos cambios:</span><span class="sxs-lookup"><span data-stu-id="82d5f-171">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="82d5f-172">Reemplace `DeviceAlertEvents` por `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="82d5f-172">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="82d5f-173">Une `AlertInfo` las tablas y las para obtener datos `AlertEvidence` `AlertId` equivalentes.</span><span class="sxs-lookup"><span data-stu-id="82d5f-173">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="82d5f-174">Consulta original</span><span class="sxs-lookup"><span data-stu-id="82d5f-174">Original query</span></span>
<span data-ttu-id="82d5f-175">La siguiente consulta usa `DeviceAlertEvents` en Microsoft Defender for Endpoint para obtener las alertas que implican _powershell.exe_:</span><span class="sxs-lookup"><span data-stu-id="82d5f-175">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="82d5f-176">Consulta modificada</span><span class="sxs-lookup"><span data-stu-id="82d5f-176">Modified query</span></span>
<span data-ttu-id="82d5f-177">La siguiente consulta se ha ajustado para su uso en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="82d5f-177">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="82d5f-178">En lugar de comprobar el nombre de archivo directamente desde , se une y `DeviceAlertEvents` comprueba el nombre de archivo en esa `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="82d5f-178">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="82d5f-179">Migrar reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="82d5f-179">Migrate custom detection rules</span></span>

<span data-ttu-id="82d5f-180">Cuando las reglas de Microsoft Defender para extremo se editan en Microsoft 365 Defender, siguen funcionando como antes si la consulta resultante solo mira las tablas de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="82d5f-180">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="82d5f-181">Por ejemplo, las alertas generadas por reglas de detección personalizadas que consultan solo tablas de dispositivos se seguirán entregando a siem y generarán notificaciones por correo electrónico, según cómo las haya configurado en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="82d5f-181">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="82d5f-182">Las reglas de supresión existentes en Defender for Endpoint también se seguirán aplicando.</span><span class="sxs-lookup"><span data-stu-id="82d5f-182">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="82d5f-183">Una vez que edite una regla defender para extremo para que consulta las tablas de identidad y correo electrónico, que solo están disponibles en Microsoft 365 Defender, la regla se mueve automáticamente a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="82d5f-183">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="82d5f-184">Alertas generadas por la regla migrada:</span><span class="sxs-lookup"><span data-stu-id="82d5f-184">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="82d5f-185">Ya no están visibles en el portal de Defender for Endpoint (Centro de seguridad de Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="82d5f-185">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="82d5f-186">Deje de entregarse en siem o genere notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="82d5f-186">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="82d5f-187">Para evitar este cambio, configure las notificaciones a través de Microsoft 365 Defender para obtener las alertas.</span><span class="sxs-lookup"><span data-stu-id="82d5f-187">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="82d5f-188">Puede usar la API de [Microsoft 365 Defender para](api-incident.md) recibir notificaciones de alertas de detección de clientes o incidentes relacionados.</span><span class="sxs-lookup"><span data-stu-id="82d5f-188">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="82d5f-189">Microsoft Defender no suprimirá las reglas de supresión de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="82d5f-189">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="82d5f-190">Para evitar que se generen alertas para determinados usuarios, dispositivos o buzones de correo, modifique las consultas correspondientes para excluir esas entidades explícitamente.</span><span class="sxs-lookup"><span data-stu-id="82d5f-190">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="82d5f-191">Si edita una regla de esta manera, se le pedirá confirmación antes de aplicar dichos cambios.</span><span class="sxs-lookup"><span data-stu-id="82d5f-191">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="82d5f-192">Las nuevas alertas generadas por reglas de detección personalizadas en Microsoft 365 Portal de Defender se muestran en una página de alerta que proporciona la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="82d5f-192">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="82d5f-193">Título y descripción de la alerta</span><span class="sxs-lookup"><span data-stu-id="82d5f-193">Alert title and description</span></span> 
- <span data-ttu-id="82d5f-194">Activos afectados</span><span class="sxs-lookup"><span data-stu-id="82d5f-194">Impacted assets</span></span>
- <span data-ttu-id="82d5f-195">Acciones realizadas en respuesta a la alerta</span><span class="sxs-lookup"><span data-stu-id="82d5f-195">Actions taken in response to the alert</span></span>
- <span data-ttu-id="82d5f-196">Resultados de consulta que desencadenaron la alerta</span><span class="sxs-lookup"><span data-stu-id="82d5f-196">Query results that triggered the alert</span></span> 
- <span data-ttu-id="82d5f-197">Información sobre la regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="82d5f-197">Information on the custom detection rule</span></span> 
 
> [!div class="mx-imgBorder"]
> <span data-ttu-id="82d5f-198">![Imagen de la nueva página de alerta](../../media/new-alert-page.png)</span><span class="sxs-lookup"><span data-stu-id="82d5f-198">![Image of new alert page](../../media/new-alert-page.png)</span></span>

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="82d5f-199">Escribir consultas sin DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="82d5f-199">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="82d5f-200">En el esquema Microsoft 365 Defender, las tablas y se proporcionan para dar cabida al conjunto diverso de información que acompaña a las alertas `AlertInfo` `AlertEvidence` de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="82d5f-200">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="82d5f-201">Para obtener la misma información de alerta que usó para obtener de la tabla en el esquema de Microsoft Defender para endpoint, filtre la tabla y, a continuación, una cada identificador único con la tabla, que proporciona información detallada sobre el evento y la `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` entidad.</span><span class="sxs-lookup"><span data-stu-id="82d5f-201">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="82d5f-202">Vea la consulta de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82d5f-202">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="82d5f-203">Esta consulta genera muchas más columnas que `DeviceAlertEvents` en el esquema de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="82d5f-203">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="82d5f-204">Para que los resultados sean manejables, use `project` para obtener solo las columnas que le interesan.</span><span class="sxs-lookup"><span data-stu-id="82d5f-204">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="82d5f-205">En el ejemplo siguiente se proyectan las columnas que podrían interesarle cuando la investigación detecte actividad de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82d5f-205">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="82d5f-206">Si desea filtrar por entidades específicas implicadas en las alertas, puede hacerlo especificando el tipo de entidad y el valor por el que `EntityType` desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="82d5f-206">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="82d5f-207">En el ejemplo siguiente se busca una dirección IP específica:</span><span class="sxs-lookup"><span data-stu-id="82d5f-207">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="82d5f-208">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82d5f-208">See also</span></span>
- [<span data-ttu-id="82d5f-209">Activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82d5f-209">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="82d5f-210">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="82d5f-210">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="82d5f-211">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="82d5f-211">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="82d5f-212">Búsqueda avanzada en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="82d5f-212">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)