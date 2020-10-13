---
title: Creación y administración de reglas de detección personalizadas en protección contra amenazas de Microsoft
description: Obtenga información sobre cómo crear y administrar reglas de detección personalizadas basadas en consultas de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, reglas, esquema, kusto, Microsoft 365, protección contra amenazas de Microsoft, RBAC, permisos, Microsoft defender ATP
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
ms.openlocfilehash: 85bf980f87b640df0f3767294b3c5f2059ba0ac6
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430864"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="22a32-104">Creación y administración de reglas de detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="22a32-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="22a32-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="22a32-105">**Applies to:**</span></span>
- <span data-ttu-id="22a32-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="22a32-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="22a32-107">Las reglas de detección personalizadas son reglas que se pueden diseñar y ajustar mediante consultas de [búsqueda avanzada](advanced-hunting-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="22a32-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="22a32-108">Estas reglas permiten supervisar de forma proactiva varios eventos y Estados del sistema, como la actividad de infracciones y los extremos configurados incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="22a32-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="22a32-109">Puede establecer que se ejecuten a intervalos regulares, generando alertas y realizando acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="22a32-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="22a32-110">Permisos necesarios para administrar detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="22a32-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="22a32-111">Para administrar las detecciones personalizadas, debe tener asignado uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="22a32-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="22a32-112">**Administrador de seguridad**: los usuarios con este [rol de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar la configuración de seguridad en el centro de seguridad de Microsoft 365 y en otros portales y servicios.</span><span class="sxs-lookup"><span data-stu-id="22a32-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="22a32-113">**Operador de seguridad**: los usuarios con este [rol de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar alertas y tener acceso global de solo lectura a características relacionadas con la seguridad, incluida toda la información del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22a32-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="22a32-114">Este rol es suficiente para administrar detecciones personalizadas solo si el control de acceso basado en roles (RBAC) está desactivado en ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="22a32-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="22a32-115">Si tiene configurado un RBAC, también necesitará el permiso **administrar la configuración de seguridad** para ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="22a32-115">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="22a32-116">Para administrar los permisos necesarios, un **administrador global** puede:</span><span class="sxs-lookup"><span data-stu-id="22a32-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="22a32-117">Asigne el rol de **Administrador** de seguridad o **operador de seguridad** en el centro de administración de [Microsoft 365](https://admin.microsoft.com/) en **funciones**  >  **Administrador de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="22a32-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="22a32-118">Compruebe la configuración de RBAC para Microsoft defender ATP en el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/) en **configuración**  >  **Permissions**  >  **roles**de permisos.</span><span class="sxs-lookup"><span data-stu-id="22a32-118">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="22a32-119">Seleccione el rol correspondiente para asignar el permiso **administrar la configuración de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="22a32-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="22a32-120">Para administrar las detecciones personalizadas, los **operadores de seguridad** necesitarán el permiso administrar la **configuración de seguridad** en ATP de Microsoft defender si RBAC está activado.</span><span class="sxs-lookup"><span data-stu-id="22a32-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="22a32-121">Crear una regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="22a32-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="22a32-122">1. Prepare la consulta.</span><span class="sxs-lookup"><span data-stu-id="22a32-122">1. Prepare the query.</span></span>

<span data-ttu-id="22a32-123">En el centro de seguridad de Microsoft 365, vaya a **búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="22a32-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="22a32-124">Cuando use una consulta nueva, ejecute la consulta para identificar los errores y comprender los posibles resultados.</span><span class="sxs-lookup"><span data-stu-id="22a32-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="22a32-125">Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar sólo 100 alertas cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="22a32-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="22a32-126">Antes de crear una regla, ajuste su consulta para evitar alertas por actividades normales y cotidianas.</span><span class="sxs-lookup"><span data-stu-id="22a32-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="22a32-127">Columnas necesarias en los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="22a32-127">Required columns in the query results</span></span>
<span data-ttu-id="22a32-128">Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="22a32-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="22a32-129">`Timestamp`: se usa para establecer la marca de hora para las alertas generadas</span><span class="sxs-lookup"><span data-stu-id="22a32-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="22a32-130">`ReportId`— habilita las búsquedas para los registros originales</span><span class="sxs-lookup"><span data-stu-id="22a32-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="22a32-131">Una de las siguientes columnas que identifican dispositivos, usuarios o buzones específicos:</span><span class="sxs-lookup"><span data-stu-id="22a32-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="22a32-132">`SenderFromAddress` (remitente del sobre o dirección de Return-Path)</span><span class="sxs-lookup"><span data-stu-id="22a32-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="22a32-133">`SenderMailFromAddress` (dirección del remitente mostrada por el cliente de correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="22a32-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="22a32-134">Se agregará compatibilidad con entidades adicionales a medida que se agreguen nuevas tablas al [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="22a32-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="22a32-135">Las consultas sencillas, como las que no usan el `project` `summarize` operador OR para personalizar o agregar resultados, normalmente devuelven estas columnas comunes.</span><span class="sxs-lookup"><span data-stu-id="22a32-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="22a32-136">Hay varias formas de garantizar que las consultas más complejas devuelven estas columnas.</span><span class="sxs-lookup"><span data-stu-id="22a32-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="22a32-137">Por ejemplo, si prefiere agregar y contar por entidad en una columna como `DeviceId` , puede seguir devolviendo `Timestamp` y `ReportId` obtenerlo del evento más reciente que implique a cada uno de los únicos `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="22a32-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="22a32-138">La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( `DeviceId` ) con detecciones de antivirus y usa este recuento para buscar solo los dispositivos con más de cinco detecciones.</span><span class="sxs-lookup"><span data-stu-id="22a32-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="22a32-139">Para devolver la última `Timestamp` y la correspondiente `ReportId` , se utiliza el `summarize` operador con la `arg_max` función.</span><span class="sxs-lookup"><span data-stu-id="22a32-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="22a32-140">Para mejorar el rendimiento de las consultas, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla.</span><span class="sxs-lookup"><span data-stu-id="22a32-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="22a32-141">Dado que la ejecución menos frecuente es _cada 24 horas_, el filtrado del día pasado cubrirá todos los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="22a32-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="22a32-142">2. cree una nueva regla y proporcione los detalles de la alerta.</span><span class="sxs-lookup"><span data-stu-id="22a32-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="22a32-143">Con la consulta en el editor de consultas, seleccione **crear regla de detección** y especifique los siguientes detalles de alerta:</span><span class="sxs-lookup"><span data-stu-id="22a32-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="22a32-144">**Nombre de detección**: nombre de la regla de detección</span><span class="sxs-lookup"><span data-stu-id="22a32-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="22a32-145">**Frecuencia**: intervalo para ejecutar la consulta y realizar una acción.</span><span class="sxs-lookup"><span data-stu-id="22a32-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="22a32-146">Consulte más información a continuación</span><span class="sxs-lookup"><span data-stu-id="22a32-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="22a32-147">**Título**de la alerta: título que se muestra con alertas desencadenadas por la regla</span><span class="sxs-lookup"><span data-stu-id="22a32-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="22a32-148">**Gravedad**: riesgo potencial del componente o actividad identificados por la regla</span><span class="sxs-lookup"><span data-stu-id="22a32-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="22a32-149">**Categoría**: componente de amenaza o actividad identificada por la regla</span><span class="sxs-lookup"><span data-stu-id="22a32-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="22a32-150">**Mitre att&CK**: una o varias técnicas de ataque identificadas por la regla según se documenta en el [marco de MITRE de ATT&CK](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="22a32-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="22a32-151">Esta sección está oculta para determinadas categorías de alertas, incluidos malware, ransomware, actividades sospechosas y software no deseado.</span><span class="sxs-lookup"><span data-stu-id="22a32-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="22a32-152">**Descripción**: más información sobre el componente o la actividad identificados por la regla</span><span class="sxs-lookup"><span data-stu-id="22a32-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="22a32-153">**Acciones recomendadas**: acciones adicionales que los respondedores pueden llevar a cabo en respuesta a una alerta</span><span class="sxs-lookup"><span data-stu-id="22a32-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="22a32-154">Frecuencia de la regla</span><span class="sxs-lookup"><span data-stu-id="22a32-154">Rule frequency</span></span>
<span data-ttu-id="22a32-155">Al guardar o editar una nueva regla, se ejecuta y comprueba si hay coincidencias de los últimos 30 días de datos.</span><span class="sxs-lookup"><span data-stu-id="22a32-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="22a32-156">A continuación, la regla se ejecuta de nuevo a intervalos fijos, aplicando una duración de lookback basada en la frecuencia elegida:</span><span class="sxs-lookup"><span data-stu-id="22a32-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="22a32-157">**Cada 24 horas**: se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días</span><span class="sxs-lookup"><span data-stu-id="22a32-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="22a32-158">**Cada 12 horas**: se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="22a32-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="22a32-159">**Cada 3 horas**: se ejecuta cada 3 horas y comprueba los datos de las últimas 6 horas.</span><span class="sxs-lookup"><span data-stu-id="22a32-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="22a32-160">**Cada hora**: se ejecuta cada hora y se comprueban los datos de las últimas dos horas</span><span class="sxs-lookup"><span data-stu-id="22a32-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="22a32-161">Hacer coincidir los filtros de tiempo de la consulta con la duración lookback.</span><span class="sxs-lookup"><span data-stu-id="22a32-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="22a32-162">Se omiten los resultados fuera de la duración de lookback.</span><span class="sxs-lookup"><span data-stu-id="22a32-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="22a32-163">Seleccione la frecuencia que coincida con el grado en el que desea supervisar las detecciones.</span><span class="sxs-lookup"><span data-stu-id="22a32-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="22a32-164">Considere la capacidad de su organización para responder a las alertas.</span><span class="sxs-lookup"><span data-stu-id="22a32-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="22a32-165">3. Elija las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="22a32-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="22a32-166">Identifique las columnas de los resultados de la consulta en las que espera buscar la entidad afectada principal o afectada.</span><span class="sxs-lookup"><span data-stu-id="22a32-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="22a32-167">Por ejemplo, una consulta puede devolver direcciones de remitente ( `SenderFromAddress` o `SenderMailFromAddress` ) y destinatario ( `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="22a32-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="22a32-168">La identificación de las columnas que representan la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta objetivo.</span><span class="sxs-lookup"><span data-stu-id="22a32-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="22a32-169">Puede seleccionar solo una columna para cada tipo de entidad (buzón, usuario o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="22a32-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="22a32-170">No se pueden seleccionar las columnas que no se devuelven mediante la consulta.</span><span class="sxs-lookup"><span data-stu-id="22a32-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="22a32-171">4. especificar acciones.</span><span class="sxs-lookup"><span data-stu-id="22a32-171">4. Specify actions.</span></span>
<span data-ttu-id="22a32-172">La regla de detección personalizada puede realizar acciones de forma automática en dispositivos, archivos o usuarios devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="22a32-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="22a32-173">Acciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="22a32-173">Actions on devices</span></span>
<span data-ttu-id="22a32-174">Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="22a32-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="22a32-175">**Aislar dispositivo**: usa ATP de Microsoft defender para aplicar el aislamiento de red completo, lo que impide que el dispositivo se conecte a cualquier aplicación o servicio.</span><span class="sxs-lookup"><span data-stu-id="22a32-175">**Isolate device**—uses Microsoft Defender ATP to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="22a32-176">Más información acerca del aislamiento de máquina ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="22a32-176">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="22a32-177">**Collect Investigation Package**: recopila información de dispositivos en un archivo zip.</span><span class="sxs-lookup"><span data-stu-id="22a32-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="22a32-178">Más información sobre el paquete de investigación ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="22a32-178">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="22a32-179">**Ejecutar detección de virus**: realiza un examen completo del antivirus de Windows Defender en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22a32-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="22a32-180">**Iniciar investigación**: inicia una [investigación automatizada](mtp-autoir.md) en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22a32-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="22a32-181">**Restringir la ejecución**de la aplicación: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos firmados con un certificado emitido por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22a32-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="22a32-182">Obtenga más información sobre las restricciones de aplicaciones con ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="22a32-182">Learn more about app restrictions with Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="22a32-183">Acciones en archivos</span><span class="sxs-lookup"><span data-stu-id="22a32-183">Actions on files</span></span>
<span data-ttu-id="22a32-184">Al seleccionar esta opción, puede elegir aplicar la acción del **archivo de cuarentena** en los archivos de la `SHA1` columna,, `InitiatingProcessSHA1` `SHA256` o de los `InitiatingProcessSHA256` resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="22a32-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="22a32-185">Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="22a32-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="22a32-186">Acciones en los usuarios</span><span class="sxs-lookup"><span data-stu-id="22a32-186">Actions on users</span></span>
<span data-ttu-id="22a32-187">Cuando se selecciona, la acción **marcar usuario como comprometedo** se lleva a cabo en los usuarios de la `AccountObjectId` `InitiatingProcessAccountObjectId` columna, o `RecipientObjectId` de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="22a32-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="22a32-188">Esta acción establece el nivel de riesgo de los usuarios en "alto" en Azure Active Directory, activando [las directivas de protección de identidad](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)correspondientes.</span><span class="sxs-lookup"><span data-stu-id="22a32-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="22a32-189">La acción permitir o bloquear para reglas de detección personalizadas no es compatible actualmente con la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22a32-189">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="22a32-190">5. establezca el ámbito de la regla.</span><span class="sxs-lookup"><span data-stu-id="22a32-190">5. Set the rule scope.</span></span>
<span data-ttu-id="22a32-191">Establezca el ámbito para especificar los dispositivos que cubre la regla.</span><span class="sxs-lookup"><span data-stu-id="22a32-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="22a32-192">El ámbito influye en las reglas que comprueban los dispositivos y no afectan a las reglas que solo comprueban buzones de correo y cuentas de usuario o identidades.</span><span class="sxs-lookup"><span data-stu-id="22a32-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="22a32-193">Al establecer el ámbito, puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="22a32-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="22a32-194">Todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="22a32-194">All devices</span></span>
- <span data-ttu-id="22a32-195">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="22a32-195">Specific device groups</span></span>

<span data-ttu-id="22a32-196">Solo se consultarán los datos de los dispositivos en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="22a32-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="22a32-197">Además, las acciones solo se realizarán en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="22a32-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="22a32-198">6. Revise y active la regla.</span><span class="sxs-lookup"><span data-stu-id="22a32-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="22a32-199">Después de revisar la regla, seleccione **crear** para guardarla.</span><span class="sxs-lookup"><span data-stu-id="22a32-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="22a32-200">La regla de detección personalizada se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="22a32-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="22a32-201">Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y tomar acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="22a32-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="22a32-202">Administración de reglas de detección personalizadas existentes</span><span class="sxs-lookup"><span data-stu-id="22a32-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="22a32-203">Puede ver la lista de reglas de detección personalizadas existentes, comprobar las ejecuciones anteriores y revisar las alertas que han desencadenado.</span><span class="sxs-lookup"><span data-stu-id="22a32-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="22a32-204">También puede ejecutar una regla según demanda y modificarla.</span><span class="sxs-lookup"><span data-stu-id="22a32-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="22a32-205">Ver las reglas existentes</span><span class="sxs-lookup"><span data-stu-id="22a32-205">View existing rules</span></span>

<span data-ttu-id="22a32-206">Para ver todas las reglas de detección personalizadas existentes, vaya a **búsqueda**de  >  **detecciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="22a32-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="22a32-207">La página enumera todas las reglas con la siguiente información de ejecución:</span><span class="sxs-lookup"><span data-stu-id="22a32-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="22a32-208">**Última ejecución**: cuando se ejecutó una regla por última vez para buscar coincidencias de consulta y generar alertas</span><span class="sxs-lookup"><span data-stu-id="22a32-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="22a32-209">**Último estado de ejecución**: Si una regla se ejecutó correctamente</span><span class="sxs-lookup"><span data-stu-id="22a32-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="22a32-210">**Próxima ejecución**: la siguiente ejecución programada</span><span class="sxs-lookup"><span data-stu-id="22a32-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="22a32-211">**Estado**: Si una regla se ha activado o desactivado</span><span class="sxs-lookup"><span data-stu-id="22a32-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="22a32-212">Ver detalles de la regla, modificar regla y ejecutar regla</span><span class="sxs-lookup"><span data-stu-id="22a32-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="22a32-213">Para ver información completa sobre una regla de detección personalizada, vaya a **búsqueda**  >  de**detecciones personalizadas** y, a continuación, seleccione el nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="22a32-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="22a32-214">A continuación, puede ver información general sobre la regla, incluida la información sobre su estado de ejecución y su ámbito.</span><span class="sxs-lookup"><span data-stu-id="22a32-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="22a32-215">La página también proporciona la lista de alertas y acciones desencadenadas.</span><span class="sxs-lookup"><span data-stu-id="22a32-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="22a32-216">![Página de detalles de la regla de detección personalizada](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="22a32-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="22a32-217">*Detalles de la regla de detección personalizada*</span><span class="sxs-lookup"><span data-stu-id="22a32-217">*Custom detection rule details*</span></span>

<span data-ttu-id="22a32-218">También puede llevar a cabo las siguientes acciones en la regla de esta página:</span><span class="sxs-lookup"><span data-stu-id="22a32-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="22a32-219">**Ejecutar**: ejecute la regla inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="22a32-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="22a32-220">Esto también restablece el intervalo para la siguiente ejecución.</span><span class="sxs-lookup"><span data-stu-id="22a32-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="22a32-221">**Editar**: modificar la regla sin cambiar la consulta</span><span class="sxs-lookup"><span data-stu-id="22a32-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="22a32-222">**Modificar consulta**: editar la consulta en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="22a32-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="22a32-223">**Activar**  /  **Desactivar**: habilitar la regla o impedir que se ejecute</span><span class="sxs-lookup"><span data-stu-id="22a32-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="22a32-224">**Eliminar**: Desactive la regla y quítela</span><span class="sxs-lookup"><span data-stu-id="22a32-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="22a32-225">Ver y administrar las alertas desencadenadas</span><span class="sxs-lookup"><span data-stu-id="22a32-225">View and manage triggered alerts</span></span>

<span data-ttu-id="22a32-226">En la pantalla detalles de la regla (**búsqueda**de  >  **detecciones personalizadas**  >  **[nombre de la regla]**), vaya a **alertas desencadenadas**, que enumera las alertas generadas por coincidencias en la regla.</span><span class="sxs-lookup"><span data-stu-id="22a32-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="22a32-227">Seleccione una alerta para ver información detallada sobre ella y realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="22a32-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="22a32-228">Administrar la alerta estableciendo su estado y clasificación (true o false Alert)</span><span class="sxs-lookup"><span data-stu-id="22a32-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="22a32-229">Vincular la alerta a un incidente</span><span class="sxs-lookup"><span data-stu-id="22a32-229">Link the alert to an incident</span></span>
- <span data-ttu-id="22a32-230">Ejecutar la consulta que desencadenó la alerta en la caza avanzada</span><span class="sxs-lookup"><span data-stu-id="22a32-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="22a32-231">Revisión de acciones</span><span class="sxs-lookup"><span data-stu-id="22a32-231">Review actions</span></span>
<span data-ttu-id="22a32-232">En la pantalla detalles de la regla (**búsqueda**de  >  **detecciones personalizadas**  >  **[nombre de la regla]**), vaya a **acciones desencadenadas**, que enumera las acciones realizadas en función de las coincidencias de la regla.</span><span class="sxs-lookup"><span data-stu-id="22a32-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="22a32-233">Para ver rápidamente información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="22a32-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="22a32-234">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="22a32-234">Related topic</span></span>
- [<span data-ttu-id="22a32-235">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="22a32-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="22a32-236">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="22a32-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="22a32-237">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="22a32-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
