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
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080750"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="2a839-104">Migrar consultas de búsqueda avanzada de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="2a839-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2a839-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2a839-105">**Applies to:**</span></span>
- <span data-ttu-id="2a839-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a839-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2a839-107">Mueva los flujos de trabajo de búsqueda avanzada de Microsoft Defender for Endpoint para buscar de forma proactiva amenazas mediante un conjunto más amplio de datos.</span><span class="sxs-lookup"><span data-stu-id="2a839-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="2a839-108">En Microsoft 365 Defender, obtiene acceso a los datos de otras soluciones de seguridad de Microsoft 365, como:</span><span class="sxs-lookup"><span data-stu-id="2a839-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="2a839-109">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2a839-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2a839-110">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2a839-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="2a839-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2a839-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2a839-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2a839-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="2a839-113">La mayoría de los clientes de Microsoft Defender para puntos de conexión [pueden usar Microsoft 365 Defender sin licencias adicionales.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="2a839-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="2a839-114">Para empezar a realizar la transición de los flujos de trabajo de búsqueda avanzada desde Defender para endpoint, [active Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="2a839-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="2a839-115">Puede realizar la transición sin afectar a los flujos de trabajo existentes de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2a839-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="2a839-116">Las consultas guardadas permanecen intactas y las reglas de detección personalizadas siguen funcionando y generando alertas.</span><span class="sxs-lookup"><span data-stu-id="2a839-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="2a839-117">Sin embargo, estarán visibles en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2a839-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="2a839-118">Tablas de esquema solo en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a839-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="2a839-119">El esquema de búsqueda avanzada [de Microsoft 365 Defender](advanced-hunting-schema-tables.md) proporciona tablas adicionales que contienen datos de varias soluciones de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a839-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="2a839-120">Las tablas siguientes solo están disponibles en Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="2a839-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="2a839-121">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-121">Table name</span></span> | <span data-ttu-id="2a839-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a839-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="2a839-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="2a839-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="2a839-124">Archivos, direcciones IP, direcciones URL, usuarios o dispositivos asociados con alertas</span><span class="sxs-lookup"><span data-stu-id="2a839-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="2a839-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="2a839-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="2a839-126">Alertas de Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identity, incluidas la información de gravedad y las categorías de amenazas</span><span class="sxs-lookup"><span data-stu-id="2a839-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="2a839-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="2a839-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="2a839-128">Actividades relacionadas con archivos en servicios y aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="2a839-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="2a839-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="2a839-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="2a839-130">Información sobre los archivos adjuntos a los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="2a839-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="2a839-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="2a839-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="2a839-132">Eventos de correo electrónico de Microsoft 365, incluidos los eventos de entrega y bloqueo de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2a839-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="2a839-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="2a839-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="2a839-134">Eventos de seguridad que se producen después de la entrega, después de que Microsoft 365 haya entregado los correos electrónicos al buzón del destinatario</span><span class="sxs-lookup"><span data-stu-id="2a839-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="2a839-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="2a839-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="2a839-136">Información sobre las direcciones URL de los correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="2a839-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="2a839-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="2a839-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="2a839-138">Eventos que implican a un controlador de dominio local que ejecuta Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="2a839-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="2a839-139">En esta tabla se trata una serie de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="2a839-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="2a839-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="2a839-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="2a839-141">Información de cuenta de varios orígenes, incluido Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2a839-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="2a839-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="2a839-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="2a839-143">Eventos de autenticación en Active Directory y servicios en línea de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a839-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="2a839-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="2a839-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="2a839-145">Consultas de objetos de Active Directory, como usuarios, grupos, dispositivos y dominios</span><span class="sxs-lookup"><span data-stu-id="2a839-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="2a839-146">Asignar tabla DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="2a839-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="2a839-147">Las `AlertInfo` tablas y `AlertEvidence` reemplazan la tabla en el esquema de `DeviceAlertEvents` Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="2a839-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="2a839-148">Además de los datos sobre las alertas de dispositivo, estas dos tablas incluyen datos sobre alertas de identidades, aplicaciones y correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="2a839-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="2a839-149">Use la tabla siguiente para comprobar cómo se asignan `DeviceAlertEvents` las columnas a las columnas de las tablas `AlertInfo` `AlertEvidence` y.</span><span class="sxs-lookup"><span data-stu-id="2a839-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="2a839-150">Además de las columnas de la tabla siguiente, la tabla incluye muchas otras columnas que proporcionan una imagen más holística de las alertas `AlertEvidence` de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="2a839-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="2a839-151">Ver todas las columnas AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="2a839-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="2a839-152">Columna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="2a839-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="2a839-153">Dónde encontrar los mismos datos en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a839-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="2a839-154">`AlertInfo` y  `AlertEvidence` tablas</span><span class="sxs-lookup"><span data-stu-id="2a839-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="2a839-155">`AlertInfo` y  `AlertEvidence` tablas</span><span class="sxs-lookup"><span data-stu-id="2a839-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="2a839-156">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="2a839-157">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="2a839-158">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="2a839-159">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="2a839-160">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="2a839-161">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="2a839-162">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="2a839-163">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="2a839-164">`AlertEvidence` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="2a839-165">`AlertInfo` tabla</span><span class="sxs-lookup"><span data-stu-id="2a839-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="2a839-166">Esta columna se usa normalmente en Microsoft Defender para Endpoint para buscar registros relacionados en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="2a839-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="2a839-167">En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="2a839-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="2a839-168">Esta columna se usa normalmente en Microsoft Defender para Endpoint para obtener información adicional sobre eventos en otras tablas.</span><span class="sxs-lookup"><span data-stu-id="2a839-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="2a839-169">En Microsoft 365 Defender, puede obtener datos relacionados directamente desde la `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="2a839-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="2a839-170">Ajustar Las consultas existentes de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="2a839-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="2a839-171">Las consultas de Microsoft Defender para puntos de conexión funcionarán tal y como están a menos que hacen referencia a la `DeviceAlertEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="2a839-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="2a839-172">Para usar estas consultas en Microsoft 365 Defender, aplique estos cambios:</span><span class="sxs-lookup"><span data-stu-id="2a839-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="2a839-173">Reemplazar `DeviceAlertEvents` por `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="2a839-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="2a839-174">Una las `AlertInfo` tablas y las tablas para obtener datos `AlertEvidence` `AlertId` equivalentes.</span><span class="sxs-lookup"><span data-stu-id="2a839-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="2a839-175">Consulta original</span><span class="sxs-lookup"><span data-stu-id="2a839-175">Original query</span></span>
<span data-ttu-id="2a839-176">La siguiente consulta usa `DeviceAlertEvents` Microsoft Defender para Endpoint para obtener las alertas que implican _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="2a839-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="2a839-177">Consulta modificada</span><span class="sxs-lookup"><span data-stu-id="2a839-177">Modified query</span></span>
<span data-ttu-id="2a839-178">Se ha ajustado la consulta siguiente para su uso en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2a839-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="2a839-179">En lugar de comprobar el nombre de archivo directamente desde , se une y `DeviceAlertEvents` comprueba el nombre de archivo en esa `AlertEvidence` tabla.</span><span class="sxs-lookup"><span data-stu-id="2a839-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="2a839-180">Migrar reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="2a839-180">Migrate custom detection rules</span></span>

<span data-ttu-id="2a839-181">Cuando se editan las reglas de Microsoft Defender para puntos de conexión en Microsoft 365 Defender, siguen funcionando como antes si la consulta resultante solo examina las tablas del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2a839-181">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> <span data-ttu-id="2a839-182">Por ejemplo, las alertas generadas por reglas de detección personalizadas que consultan solo tablas de dispositivo se seguirán entregando a siem y generarán notificaciones por correo electrónico, en función de cómo las hayas configurado en Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2a839-182">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2a839-183">También se seguirán aplicando las reglas de supresión existentes en Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2a839-183">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="2a839-184">Una vez que edite una regla de Defender para extremo para que consulta las tablas de identidad y correo electrónico, que solo están disponibles en Microsoft 365 Defender, la regla se mueve automáticamente a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2a839-184">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="2a839-185">Alertas generadas por la regla migrada:</span><span class="sxs-lookup"><span data-stu-id="2a839-185">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="2a839-186">Ya no están visibles en el portal de Defender for Endpoint (Centro de seguridad de Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="2a839-186">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="2a839-187">Deja de entregarse a siem o genera notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2a839-187">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="2a839-188">Para evitar este cambio, configure las notificaciones a través de Microsoft 365 Defender para obtener las alertas.</span><span class="sxs-lookup"><span data-stu-id="2a839-188">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="2a839-189">Puede usar la API de [Microsoft 365 Defender](api-incident.md) para recibir notificaciones de alertas de detección de clientes o incidentes relacionados.</span><span class="sxs-lookup"><span data-stu-id="2a839-189">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="2a839-190">Microsoft Defender no suprimirá las reglas de supresión de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="2a839-190">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="2a839-191">Para evitar que se generen alertas para determinados usuarios, dispositivos o buzones, modifique las consultas correspondientes para excluir esas entidades explícitamente.</span><span class="sxs-lookup"><span data-stu-id="2a839-191">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="2a839-192">Si edita una regla de esta forma, se le pedirá confirmación antes de aplicar dichos cambios.</span><span class="sxs-lookup"><span data-stu-id="2a839-192">If you do edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="2a839-193">Las nuevas alertas generadas por reglas de detección personalizadas en el portal de Microsoft 365 Defender se muestran en una página de alerta que proporciona la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="2a839-193">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="2a839-194">Título y descripción de la alerta</span><span class="sxs-lookup"><span data-stu-id="2a839-194">Alert title and description</span></span> 
- <span data-ttu-id="2a839-195">Activos afectados</span><span class="sxs-lookup"><span data-stu-id="2a839-195">Impacted assets</span></span>
- <span data-ttu-id="2a839-196">Acciones tomadas en respuesta a la alerta</span><span class="sxs-lookup"><span data-stu-id="2a839-196">Actions taken in response to the alert</span></span>
- <span data-ttu-id="2a839-197">Resultados de la consulta que desencadenaron la alerta</span><span class="sxs-lookup"><span data-stu-id="2a839-197">Query results that triggered the alert</span></span> 
- <span data-ttu-id="2a839-198">Información sobre la regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="2a839-198">Information on the custom detection rule</span></span> 
 
![Imagen de la nueva página de alerta](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="2a839-200">Escribir consultas sin DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="2a839-200">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="2a839-201">En el esquema de Microsoft 365 Defender, las tablas y las tablas se proporcionan para dar cabida al variado conjunto de información que acompaña a las alertas `AlertInfo` `AlertEvidence` de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="2a839-201">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="2a839-202">Para obtener la misma información de alerta que usó para obtener de la tabla en el esquema de Microsoft Defender para puntos de conexión, filtre la tabla y, a continuación, una cada identificador único con la tabla, que proporciona información detallada sobre eventos y `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` entidades.</span><span class="sxs-lookup"><span data-stu-id="2a839-202">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="2a839-203">Consulta de ejemplo a continuación:</span><span class="sxs-lookup"><span data-stu-id="2a839-203">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="2a839-204">Esta consulta genera muchas más columnas que `DeviceAlertEvents` en el esquema de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="2a839-204">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="2a839-205">Para que los resultados sean fáciles de administrar, úselos para obtener solo las columnas `project` que le interesan.</span><span class="sxs-lookup"><span data-stu-id="2a839-205">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="2a839-206">En el ejemplo siguiente se muestran las columnas que pueden interesarle cuando la investigación detectó actividad de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2a839-206">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="2a839-207">Si desea filtrar por entidades específicas implicadas en las alertas, puede hacerlo especificando el tipo de entidad y el valor por el que `EntityType` desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="2a839-207">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="2a839-208">En el siguiente ejemplo se busca una dirección IP específica:</span><span class="sxs-lookup"><span data-stu-id="2a839-208">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="2a839-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a839-209">See also</span></span>
- [<span data-ttu-id="2a839-210">Activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a839-210">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2a839-211">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="2a839-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2a839-212">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="2a839-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2a839-213">Búsqueda avanzada en Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="2a839-213">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)