---
title: Crear y administrar reglas de detección personalizadas en Microsoft 365 Defender
description: Aprenda a crear y administrar reglas de detecciones personalizadas basadas en consultas de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, detecciones personalizadas, reglas, esquema, kusto, microsoft 365, Protección contra amenazas de Microsoft, RBAC, permisos, ATP de Microsoft Defender
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
ms.technology: m365d
ms.openlocfilehash: d58292f658446259bfab5b1b55c8b462d081421c
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080628"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="9eb3e-104">Crear y administrar reglas de detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="9eb3e-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9eb3e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9eb3e-105">**Applies to:**</span></span>
- <span data-ttu-id="9eb3e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9eb3e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9eb3e-107">Las reglas de detección personalizadas son reglas que se pueden diseñar y modificar mediante consultas [de búsqueda](advanced-hunting-overview.md) avanzadas.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="9eb3e-108">Estas reglas le permiten supervisar de forma proactiva varios eventos y estados del sistema, incluida la actividad sospechosa de infracciones y los puntos de conexión mal configurados.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="9eb3e-109">Puedes configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="9eb3e-110">Permisos necesarios para administrar detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="9eb3e-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="9eb3e-111">Para administrar las detecciones personalizadas, debe tener asignado uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="9eb3e-112">**Administrador de seguridad:** los usuarios con este rol [de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar la configuración de seguridad en el Centro de seguridad de Microsoft 365 y otros portales y servicios.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="9eb3e-113">**Operador de seguridad:** los usuarios con este rol de [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar alertas y tener acceso global de solo lectura a las características relacionadas con la seguridad, incluida toda la información del Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="9eb3e-114">Este rol es suficiente para administrar detecciones personalizadas solo si el control de acceso basado en roles (RBAC) está desactivado en Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9eb3e-115">Si tiene RBAC configurado, también necesita el permiso administrar la configuración **de seguridad** para Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="9eb3e-116">Para administrar los permisos necesarios, un **administrador global** puede:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="9eb3e-117">Asigne el rol **de administrador de seguridad** o operador **de** seguridad en el Centro de administración de [Microsoft 365](https://admin.microsoft.com/) en **Administración** de seguridad  >  **de roles.**</span><span class="sxs-lookup"><span data-stu-id="9eb3e-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="9eb3e-118">Compruebe la configuración de RBAC de Microsoft Defender para endpoint en el Centro [de seguridad de Microsoft Defender](https://securitycenter.windows.com/) en Roles **de** permisos  >  **de**  >  **configuración.**</span><span class="sxs-lookup"><span data-stu-id="9eb3e-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="9eb3e-119">Seleccione el rol correspondiente para asignar el permiso **administrar la configuración de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="9eb3e-120">Para administrar detecciones personalizadas,  los operadores de seguridad necesitarán el permiso administrar la configuración de seguridad en Microsoft Defender para Endpoint si RBAC está activado. </span><span class="sxs-lookup"><span data-stu-id="9eb3e-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="9eb3e-121">Crear una regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="9eb3e-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="9eb3e-122">1. Prepare la consulta.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-122">1. Prepare the query.</span></span>

<span data-ttu-id="9eb3e-123">En el Centro de seguridad de Microsoft 365, vaya a Búsqueda **avanzada** y seleccione una consulta existente o cree una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="9eb3e-124">Al usar una nueva consulta, ejecute la consulta para identificar errores y comprender los posibles resultados.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9eb3e-125">Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar solo 100 alertas cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="9eb3e-126">Antes de crear una regla, retocar la consulta para evitar alertas de actividad normal diaria.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="9eb3e-127">Columnas necesarias en los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="9eb3e-127">Required columns in the query results</span></span>
<span data-ttu-id="9eb3e-128">Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="9eb3e-129">`Timestamp`Se usa para establecer la marca de tiempo de las alertas generadas</span><span class="sxs-lookup"><span data-stu-id="9eb3e-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="9eb3e-130">`ReportId`Habilita las búsquedas de los registros originales</span><span class="sxs-lookup"><span data-stu-id="9eb3e-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="9eb3e-131">Una de las siguientes columnas que identifican dispositivos, usuarios o buzones específicos:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="9eb3e-132">`SenderFromAddress` (remitente sobre o Return-Path dirección)</span><span class="sxs-lookup"><span data-stu-id="9eb3e-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="9eb3e-133">`SenderMailFromAddress` (Dirección del remitente mostrada por el cliente de correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="9eb3e-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="9eb3e-134">Se agregará compatibilidad con entidades adicionales a medida que se agregan nuevas tablas al [esquema de búsqueda avanzada.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="9eb3e-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="9eb3e-135">Las consultas simples, como las que no usan el operador or para personalizar o agregar resultados, normalmente `project` `summarize` devuelven estas columnas comunes.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="9eb3e-136">Hay varias maneras de garantizar que las consultas más complejas devuelvan estas columnas.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="9eb3e-137">Por ejemplo, si prefiere agregar y contar por entidad bajo una columna como , todavía puede devolverlo y obtenerlo del evento más reciente que implica cada uno `DeviceId` `Timestamp` de los `ReportId` únicos `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="9eb3e-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="9eb3e-138">La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( ) con detecciones antivirus y usa este recuento para buscar solo los dispositivos con más `DeviceId` de cinco detecciones.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="9eb3e-139">Para devolver la última `Timestamp` y la `ReportId` correspondiente, usa el operador con la `summarize` `arg_max` función.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="9eb3e-140">Para mejorar el rendimiento de las consultas, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="9eb3e-141">Dado que la ejecución menos frecuente es _cada 24 horas,_ el filtrado del día anterior abarcará todos los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="9eb3e-142">2. Cree una nueva regla y proporcione detalles de alerta.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="9eb3e-143">Con la consulta en el editor de consultas, seleccione **Crear regla de detección** y especifique los siguientes detalles de alerta:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="9eb3e-144">**Nombre de la detección:** nombre de la regla de detección</span><span class="sxs-lookup"><span data-stu-id="9eb3e-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="9eb3e-145">**Frecuencia:** intervalo para ejecutar la consulta y tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="9eb3e-146">Consulta instrucciones adicionales a continuación</span><span class="sxs-lookup"><span data-stu-id="9eb3e-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="9eb3e-147">**Título de alerta:** título que se muestra con alertas desencadenadas por la regla</span><span class="sxs-lookup"><span data-stu-id="9eb3e-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="9eb3e-148">**Gravedad:** posible riesgo del componente o actividad identificado por la regla</span><span class="sxs-lookup"><span data-stu-id="9eb3e-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="9eb3e-149">**Categoría:** componente de amenaza o actividad identificada por la regla</span><span class="sxs-lookup"><span data-stu-id="9eb3e-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="9eb3e-150">**MITRE ATT&técnicas de CK:** una o más técnicas de ataque identificadas por la regla como se documentan en el marco de [miTRE ATT&CK](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="9eb3e-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="9eb3e-151">Esta sección está oculta para determinadas categorías de alertas, como malware, ransomware, actividad sospechosa y software no deseado</span><span class="sxs-lookup"><span data-stu-id="9eb3e-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="9eb3e-152">**Descripción:** más información sobre el componente o la actividad identificados por la regla</span><span class="sxs-lookup"><span data-stu-id="9eb3e-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="9eb3e-153">**Acciones recomendadas:** acciones adicionales que los respondedores pueden realizar en respuesta a una alerta</span><span class="sxs-lookup"><span data-stu-id="9eb3e-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="9eb3e-154">Frecuencia de regla</span><span class="sxs-lookup"><span data-stu-id="9eb3e-154">Rule frequency</span></span>
<span data-ttu-id="9eb3e-155">Cuando guarda o edita una regla nueva, se ejecuta y comprueba si hay coincidencias de los últimos 30 días de datos.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="9eb3e-156">A continuación, la regla se ejecuta de nuevo a intervalos fijos, aplicando una duración de recuperación en función de la frecuencia que elija:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="9eb3e-157">**Cada 24 horas:** se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días</span><span class="sxs-lookup"><span data-stu-id="9eb3e-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="9eb3e-158">**Cada 12 horas:** se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="9eb3e-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="9eb3e-159">**Cada 3 horas:** se ejecuta cada 3 horas, comprobando los datos de las últimas 6 horas</span><span class="sxs-lookup"><span data-stu-id="9eb3e-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="9eb3e-160">**Cada hora:** se ejecuta cada hora, comprobando los datos de las últimas 2 horas</span><span class="sxs-lookup"><span data-stu-id="9eb3e-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="9eb3e-161">Hacer coincidir los filtros de tiempo de la consulta con la duración de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="9eb3e-162">Los resultados fuera de la duración de la devolución se omiten.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="9eb3e-163">Seleccione la frecuencia que coincida con la proximidad con la que desea supervisar las detecciones.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="9eb3e-164">Tenga en cuenta la capacidad de su organización para responder a las alertas.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="9eb3e-165">3. Elija las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="9eb3e-166">Identifique las columnas de los resultados de la consulta donde espera encontrar la entidad principal afectada o afectada.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="9eb3e-167">Por ejemplo, una consulta puede devolver direcciones de remitente ( `SenderFromAddress` o ) y destinatario ( `SenderMailFromAddress` `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="9eb3e-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="9eb3e-168">Identificar cuál de estas columnas representa la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta de destino.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="9eb3e-169">Solo puede seleccionar una columna para cada tipo de entidad (buzón, usuario o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="9eb3e-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="9eb3e-170">Las columnas que no devuelve la consulta no se pueden seleccionar.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="9eb3e-171">4. Especificar acciones.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-171">4. Specify actions.</span></span>
<span data-ttu-id="9eb3e-172">La regla de detección personalizada puede realizar automáticamente acciones en dispositivos, archivos o usuarios devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="9eb3e-173">Acciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="9eb3e-173">Actions on devices</span></span>
<span data-ttu-id="9eb3e-174">Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="9eb3e-175">**Aislar dispositivo:** usa Microsoft Defender para Endpoint para aplicar el aislamiento de red completo, evitando que el dispositivo se conecte a cualquier aplicación o servicio.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="9eb3e-176">Más información sobre el aislamiento de la máquina de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="9eb3e-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="9eb3e-177">**Recopilar paquete de investigación:** recopila información del dispositivo en un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="9eb3e-178">Más información sobre el paquete de investigación de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="9eb3e-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="9eb3e-179">**Ejecutar examen antivirus:** realiza un análisis completo Windows Defender antivirus en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="9eb3e-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="9eb3e-180">**Iniciar investigación:** inicia una [investigación automatizada](mtp-autoir.md) en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="9eb3e-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="9eb3e-181">**Restringir la ejecución de** la aplicación: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos firmados con un certificado emitido por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="9eb3e-182">Más información sobre las restricciones de la aplicación con Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="9eb3e-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="9eb3e-183">Acciones en archivos</span><span class="sxs-lookup"><span data-stu-id="9eb3e-183">Actions on files</span></span>
<span data-ttu-id="9eb3e-184">Cuando se selecciona, puede optar por aplicar la **acción** De poner en cuarentena archivo en los archivos de la `SHA1` , , o columna de los `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="9eb3e-185">Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="9eb3e-186">Acciones en los usuarios</span><span class="sxs-lookup"><span data-stu-id="9eb3e-186">Actions on users</span></span>
<span data-ttu-id="9eb3e-187">Cuando se selecciona, la acción Marcar **usuario** como comprometida se toma en los usuarios de la columna , o en la `AccountObjectId` columna de los `InitiatingProcessAccountObjectId` `RecipientObjectId` resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="9eb3e-188">Esta acción establece el nivel de riesgo de los usuarios en "alto" en Azure Active Directory, lo que desencadena las directivas de [protección de identidades correspondientes.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="9eb3e-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="9eb3e-189">La acción permitir o bloquear para reglas de detección personalizadas no se admite actualmente en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="9eb3e-190">5. Establecer el ámbito de regla.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-190">5. Set the rule scope.</span></span>
<span data-ttu-id="9eb3e-191">Establece el ámbito para especificar qué dispositivos están cubiertos por la regla.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="9eb3e-192">El ámbito influye en las reglas que comprueban dispositivos y no afecta a las reglas que solo comprueban buzones de correo, cuentas de usuario o identidades.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="9eb3e-193">Al establecer el ámbito, puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="9eb3e-194">Todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="9eb3e-194">All devices</span></span>
- <span data-ttu-id="9eb3e-195">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="9eb3e-195">Specific device groups</span></span>

<span data-ttu-id="9eb3e-196">Solo se consultarán los datos de dispositivos en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="9eb3e-197">Además, las acciones solo se realizarán en esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="9eb3e-198">6. Revisar y activar la regla.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="9eb3e-199">Después de revisar la regla, seleccione **Crear** para guardarla.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="9eb3e-200">La regla de detección personalizada se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="9eb3e-201">Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y realizar acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="9eb3e-202">Administrar reglas de detección personalizadas existentes</span><span class="sxs-lookup"><span data-stu-id="9eb3e-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="9eb3e-203">Puedes ver la lista de reglas de detección personalizadas existentes, comprobar sus ejecuciones anteriores y revisar las alertas que han activado.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="9eb3e-204">También puede ejecutar una regla a petición y modificarla.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="9eb3e-205">Ver reglas existentes</span><span class="sxs-lookup"><span data-stu-id="9eb3e-205">View existing rules</span></span>

<span data-ttu-id="9eb3e-206">Para ver todas las reglas de detección personalizadas existentes, vaya **a**  >  **Detecciones personalizadas de búsqueda.**</span><span class="sxs-lookup"><span data-stu-id="9eb3e-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="9eb3e-207">La página enumera todas las reglas con la siguiente información de ejecución:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="9eb3e-208">**Última ejecución:** cuando se ha ejecutado una regla por última vez para comprobar si hay coincidencias de consulta y generar alertas</span><span class="sxs-lookup"><span data-stu-id="9eb3e-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="9eb3e-209">**Estado de la última ejecución:** si una regla se ejecutó correctamente</span><span class="sxs-lookup"><span data-stu-id="9eb3e-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="9eb3e-210">**Siguiente ejecución:** la siguiente ejecución programada</span><span class="sxs-lookup"><span data-stu-id="9eb3e-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="9eb3e-211">**Estado:** si una regla se ha activado o desactivado</span><span class="sxs-lookup"><span data-stu-id="9eb3e-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="9eb3e-212">Ver detalles de la regla, modificar regla y ejecutar regla</span><span class="sxs-lookup"><span data-stu-id="9eb3e-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="9eb3e-213">Para ver información completa acerca de una regla de detección personalizada, vaya a Detecciones personalizadas de búsqueda y, a continuación,  >   seleccione el nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="9eb3e-214">A continuación, puede ver información general sobre la regla, incluida la información sobre su estado de ejecución y ámbito.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="9eb3e-215">La página también proporciona la lista de alertas y acciones desencadenadas.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="9eb3e-216">![Página de detalles de la regla de detección personalizada](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="9eb3e-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="9eb3e-217">*Detalles de la regla de detección personalizada*</span><span class="sxs-lookup"><span data-stu-id="9eb3e-217">*Custom detection rule details*</span></span>

<span data-ttu-id="9eb3e-218">También puede realizar las siguientes acciones en la regla desde esta página:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="9eb3e-219">**Ejecutar:** ejecute la regla inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="9eb3e-220">Esto también restablece el intervalo de la siguiente ejecución.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="9eb3e-221">**Editar:** modificar la regla sin cambiar la consulta</span><span class="sxs-lookup"><span data-stu-id="9eb3e-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="9eb3e-222">**Modificar consulta:** editar la consulta en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="9eb3e-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="9eb3e-223">**Activar**  /  **Desactivar:** habilitar la regla o impedir que se ejecute</span><span class="sxs-lookup"><span data-stu-id="9eb3e-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="9eb3e-224">**Eliminar:** desactivar la regla y quitarla</span><span class="sxs-lookup"><span data-stu-id="9eb3e-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="9eb3e-225">Ver y administrar alertas desencadenadas</span><span class="sxs-lookup"><span data-stu-id="9eb3e-225">View and manage triggered alerts</span></span>

<span data-ttu-id="9eb3e-226">En la pantalla de detalles de la regla (**detecciones** personalizadas de búsqueda [nombre de regla] ), vaya a Alertas desencadenadas , que enumera las  >  **alertas generadas** por coincidencias  >  con la regla. </span><span class="sxs-lookup"><span data-stu-id="9eb3e-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="9eb3e-227">Seleccione una alerta para ver información detallada sobre ella y realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9eb3e-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="9eb3e-228">Administrar la alerta estableciendo su estado y clasificación (alerta verdadera o falsa)</span><span class="sxs-lookup"><span data-stu-id="9eb3e-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="9eb3e-229">Vincular la alerta a un incidente</span><span class="sxs-lookup"><span data-stu-id="9eb3e-229">Link the alert to an incident</span></span>
- <span data-ttu-id="9eb3e-230">Ejecutar la consulta que desencadenó la alerta en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="9eb3e-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="9eb3e-231">Revisar acciones</span><span class="sxs-lookup"><span data-stu-id="9eb3e-231">Review actions</span></span>
<span data-ttu-id="9eb3e-232">En la pantalla de detalles de la regla **(** detecciones personalizadas de búsqueda [nombre de regla] ), vaya a Acciones desencadenadas , que enumera las acciones realizadas en función de las  >  **coincidencias** con la  >   regla.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="9eb3e-233">Para ver rápidamente la información y realizar una acción en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9eb3e-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="9eb3e-234">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9eb3e-234">See also</span></span>
- [<span data-ttu-id="9eb3e-235">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="9eb3e-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="9eb3e-236">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="9eb3e-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9eb3e-237">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="9eb3e-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9eb3e-238">Migrar consultas de búsqueda avanzada de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="9eb3e-238">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)
