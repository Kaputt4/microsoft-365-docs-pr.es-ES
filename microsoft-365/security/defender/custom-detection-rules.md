---
title: Crear y administrar reglas de detección personalizadas en Microsoft 365 Defender
description: Obtenga información sobre cómo crear y administrar reglas de detecciones personalizadas basadas en consultas avanzadas de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, reglas, esquema, kusto, RBAC, permisos, Microsoft Defender para endpoint
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
ms.openlocfilehash: f37cc63c958331f7c03e09689de92c73fd06b4d4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952565"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="3c79a-104">Crear y administrar reglas de detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="3c79a-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3c79a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3c79a-105">**Applies to:**</span></span>
- <span data-ttu-id="3c79a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c79a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="3c79a-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3c79a-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="3c79a-108">Las reglas de detección personalizadas son reglas que puedes diseñar y ajustar [con](advanced-hunting-overview.md) consultas avanzadas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3c79a-108">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="3c79a-109">Estas reglas le permiten supervisar proactivamente varios eventos y estados del sistema, incluidos la actividad de infracción sospechosa y los extremos mal configurados.</span><span class="sxs-lookup"><span data-stu-id="3c79a-109">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="3c79a-110">Puede configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="3c79a-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="3c79a-111">Permisos necesarios para administrar detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="3c79a-111">Required permissions for managing custom detections</span></span>

<span data-ttu-id="3c79a-112">Para administrar detecciones personalizadas, debe tener asignado uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="3c79a-112">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="3c79a-113">**Administrador de** seguridad: los usuarios [con este Azure Active Directory pueden](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) administrar la configuración de seguridad en Microsoft 365 de seguridad y otros portales y servicios.</span><span class="sxs-lookup"><span data-stu-id="3c79a-113">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="3c79a-114">**Operador de** seguridad: los usuarios con este [rol Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar alertas y tener acceso global de solo lectura a las características relacionadas con la seguridad, incluida toda la información del Microsoft 365 de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3c79a-114">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="3c79a-115">Este rol es suficiente para administrar detecciones personalizadas solo si el control de acceso basado en roles (RBAC) está desactivado en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="3c79a-115">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3c79a-116">Si tiene RBAC configurado, también necesita el permiso administrar la configuración **de seguridad** para Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="3c79a-116">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="3c79a-117">Para administrar los permisos necesarios, un **administrador global** puede:</span><span class="sxs-lookup"><span data-stu-id="3c79a-117">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="3c79a-118">Asigne el **rol de administrador de seguridad** o operador **de** seguridad en Microsoft 365 centro [de administración](https://admin.microsoft.com/) en **Roles**  >  **Security admin**.</span><span class="sxs-lookup"><span data-stu-id="3c79a-118">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="3c79a-119">Compruebe la configuración de RBAC para Microsoft Defender para endpoint [en Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com/) en **Configuración** roles  >  **de permisos**  >  .</span><span class="sxs-lookup"><span data-stu-id="3c79a-119">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="3c79a-120">Seleccione el rol correspondiente para asignar el **permiso administrar la configuración de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="3c79a-120">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="3c79a-121">Para administrar detecciones personalizadas,  los operadores de seguridad necesitarán el permiso administrar la configuración de seguridad en Microsoft Defender para endpoint si RBAC está activado. </span><span class="sxs-lookup"><span data-stu-id="3c79a-121">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="3c79a-122">Crear una regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="3c79a-122">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="3c79a-123">1. Prepare la consulta.</span><span class="sxs-lookup"><span data-stu-id="3c79a-123">1. Prepare the query.</span></span>

<span data-ttu-id="3c79a-124">En Microsoft 365 seguridad, vaya a **Búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="3c79a-124">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="3c79a-125">Al usar una nueva consulta, ejecute la consulta para identificar errores y comprender los posibles resultados.</span><span class="sxs-lookup"><span data-stu-id="3c79a-125">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3c79a-126">Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar solo 100 alertas cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="3c79a-126">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="3c79a-127">Antes de crear una regla, ajusta la consulta para evitar alertas de actividad normal del día a día.</span><span class="sxs-lookup"><span data-stu-id="3c79a-127">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="3c79a-128">Columnas necesarias en los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="3c79a-128">Required columns in the query results</span></span>
<span data-ttu-id="3c79a-129">Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="3c79a-129">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="3c79a-130">`Timestamp`— se usa para establecer la marca de tiempo de las alertas generadas</span><span class="sxs-lookup"><span data-stu-id="3c79a-130">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="3c79a-131">`ReportId`: habilita las búsquedas de los registros originales</span><span class="sxs-lookup"><span data-stu-id="3c79a-131">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="3c79a-132">Una de las siguientes columnas que identifican dispositivos, usuarios o buzones específicos:</span><span class="sxs-lookup"><span data-stu-id="3c79a-132">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="3c79a-133">`SenderFromAddress` (remitente de sobre o Return-Path dirección)</span><span class="sxs-lookup"><span data-stu-id="3c79a-133">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="3c79a-134">`SenderMailFromAddress` (dirección de remitente mostrada por el cliente de correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="3c79a-134">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="3c79a-135">Se agregará compatibilidad con entidades adicionales a medida que se agregan nuevas tablas al [esquema de búsqueda avanzada.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="3c79a-135">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="3c79a-136">Las consultas simples, como las que no usan el operador or para personalizar o agregar resultados, normalmente `project` `summarize` devuelven estas columnas comunes.</span><span class="sxs-lookup"><span data-stu-id="3c79a-136">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="3c79a-137">Hay varias maneras de garantizar que las consultas más complejas devuelvan estas columnas.</span><span class="sxs-lookup"><span data-stu-id="3c79a-137">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="3c79a-138">Por ejemplo, si prefiere agregar y contar por entidad debajo de una columna como , todavía puede devolver y obtenerlo del evento más reciente que implica cada `DeviceId` `Timestamp` único `ReportId` `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="3c79a-138">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="3c79a-139">La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( ) con detecciones antivirus y usa este recuento para buscar solo los dispositivos con más `DeviceId` de cinco detecciones.</span><span class="sxs-lookup"><span data-stu-id="3c79a-139">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="3c79a-140">Para devolver el último `Timestamp` y el correspondiente , usa el operador con la `ReportId` `summarize` `arg_max` función.</span><span class="sxs-lookup"><span data-stu-id="3c79a-140">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="3c79a-141">Para obtener un mejor rendimiento de consulta, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla.</span><span class="sxs-lookup"><span data-stu-id="3c79a-141">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="3c79a-142">Dado que la ejecución menos frecuente es _cada 24 horas,_ el filtrado del último día cubrirá todos los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="3c79a-142">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="3c79a-143">2. Cree una nueva regla y proporcione detalles de alerta.</span><span class="sxs-lookup"><span data-stu-id="3c79a-143">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="3c79a-144">Con la consulta en el editor de consultas, seleccione **Crear regla de detección** y especifique los siguientes detalles de alerta:</span><span class="sxs-lookup"><span data-stu-id="3c79a-144">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="3c79a-145">**Nombre de detección**: nombre de la regla de detección</span><span class="sxs-lookup"><span data-stu-id="3c79a-145">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="3c79a-146">**Frecuencia:** intervalo para ejecutar la consulta y realizar acciones.</span><span class="sxs-lookup"><span data-stu-id="3c79a-146">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="3c79a-147">Vea instrucciones adicionales a continuación</span><span class="sxs-lookup"><span data-stu-id="3c79a-147">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="3c79a-148">**Título de alerta:** título que se muestra con alertas desencadenadas por la regla</span><span class="sxs-lookup"><span data-stu-id="3c79a-148">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="3c79a-149">**Gravedad:** riesgo potencial del componente o actividad identificado por la regla</span><span class="sxs-lookup"><span data-stu-id="3c79a-149">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="3c79a-150">**Categoría**: componente de amenaza o actividad identificada por la regla</span><span class="sxs-lookup"><span data-stu-id="3c79a-150">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="3c79a-151">**MITRE ATT&técnicas de CK**: una o más técnicas de ataque identificadas por la regla como documentadas en el marco de&[CK de MITRE ATT](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="3c79a-151">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="3c79a-152">Esta sección está oculta para determinadas categorías de alertas, como malware, ransomware, actividad sospechosa y software no deseado</span><span class="sxs-lookup"><span data-stu-id="3c79a-152">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="3c79a-153">**Descripción:** más información sobre el componente o la actividad identificada por la regla</span><span class="sxs-lookup"><span data-stu-id="3c79a-153">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="3c79a-154">**Acciones recomendadas:** acciones adicionales que los respondedores pueden realizar en respuesta a una alerta</span><span class="sxs-lookup"><span data-stu-id="3c79a-154">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="3c79a-155">Frecuencia de regla</span><span class="sxs-lookup"><span data-stu-id="3c79a-155">Rule frequency</span></span>
<span data-ttu-id="3c79a-156">Al guardar una nueva regla, se ejecuta y comprueba las coincidencias de los últimos 30 días de datos.</span><span class="sxs-lookup"><span data-stu-id="3c79a-156">When you save a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="3c79a-157">A continuación, la regla se ejecuta de nuevo a intervalos fijos, aplicando una duración de devolución basada en la frecuencia que elija:</span><span class="sxs-lookup"><span data-stu-id="3c79a-157">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="3c79a-158">**Cada 24 horas:** se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días</span><span class="sxs-lookup"><span data-stu-id="3c79a-158">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="3c79a-159">**Cada 12 horas:** se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="3c79a-159">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="3c79a-160">**Cada 3 horas:** se ejecuta cada 3 horas, comprobando los datos de las últimas 6 horas</span><span class="sxs-lookup"><span data-stu-id="3c79a-160">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="3c79a-161">**Cada hora:** se ejecuta cada hora, comprobando los datos de las últimas 2 horas</span><span class="sxs-lookup"><span data-stu-id="3c79a-161">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="3c79a-162">Al editar una regla, se ejecutará con los cambios aplicados en la siguiente hora de ejecución programada según la frecuencia que establezca.</span><span class="sxs-lookup"><span data-stu-id="3c79a-162">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>



>[!TIP]
> <span data-ttu-id="3c79a-163">Coincide con los filtros de tiempo de la consulta con la duración de la devolución.</span><span class="sxs-lookup"><span data-stu-id="3c79a-163">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="3c79a-164">Se omiten los resultados fuera de la duración de la devolución.</span><span class="sxs-lookup"><span data-stu-id="3c79a-164">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="3c79a-165">Seleccione la frecuencia que coincida con la que desea supervisar las detecciones.</span><span class="sxs-lookup"><span data-stu-id="3c79a-165">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="3c79a-166">Tenga en cuenta la capacidad de su organización para responder a las alertas.</span><span class="sxs-lookup"><span data-stu-id="3c79a-166">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="3c79a-167">3. Elija las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="3c79a-167">3. Choose the impacted entities.</span></span>
<span data-ttu-id="3c79a-168">Identifique las columnas de los resultados de la consulta en las que espera encontrar la entidad principal afectada o afectada.</span><span class="sxs-lookup"><span data-stu-id="3c79a-168">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="3c79a-169">Por ejemplo, una consulta puede devolver direcciones de remitente ( `SenderFromAddress` o ) y destinatario ( `SenderMailFromAddress` `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="3c79a-169">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="3c79a-170">La identificación de cuál de estas columnas representa la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta de destino.</span><span class="sxs-lookup"><span data-stu-id="3c79a-170">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="3c79a-171">Solo puede seleccionar una columna para cada tipo de entidad (buzón, usuario o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="3c79a-171">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="3c79a-172">Las columnas que la consulta no devuelve no se pueden seleccionar.</span><span class="sxs-lookup"><span data-stu-id="3c79a-172">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="3c79a-173">4. Especifique acciones.</span><span class="sxs-lookup"><span data-stu-id="3c79a-173">4. Specify actions.</span></span>
<span data-ttu-id="3c79a-174">La regla de detección personalizada puede realizar automáticamente acciones en dispositivos, archivos o usuarios devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="3c79a-174">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="3c79a-175">Acciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="3c79a-175">Actions on devices</span></span>
<span data-ttu-id="3c79a-176">Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="3c79a-176">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="3c79a-177">**Aislar dispositivo:** usa Microsoft Defender para Endpoint para aplicar aislamiento total de red, lo que impide que el dispositivo se conecte a cualquier aplicación o servicio.</span><span class="sxs-lookup"><span data-stu-id="3c79a-177">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="3c79a-178">Más información sobre el aislamiento de la máquina de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="3c79a-178">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="3c79a-179">**Recopilar paquete de investigación:** recopila información del dispositivo en un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="3c79a-179">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="3c79a-180">Obtenga más información sobre el paquete de investigación de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="3c79a-180">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="3c79a-181">**Ejecutar examen antivirus:** realiza un examen Antivirus de Windows Defender completo en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="3c79a-181">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="3c79a-182">**Iniciar investigación:** inicia una [investigación automatizada](m365d-autoir.md) en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="3c79a-182">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="3c79a-183">**Restringir la ejecución de** aplicaciones: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos que están firmados con un certificado emitido por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c79a-183">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="3c79a-184">Más información sobre las restricciones de la aplicación con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="3c79a-184">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="3c79a-185">Acciones en archivos</span><span class="sxs-lookup"><span data-stu-id="3c79a-185">Actions on files</span></span>
<span data-ttu-id="3c79a-186">Cuando se selecciona, puede optar por aplicar la acción Archivo **de** cuarentena en los archivos de `SHA1` la columna , , o de los `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="3c79a-186">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="3c79a-187">Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="3c79a-187">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="3c79a-188">Acciones en usuarios</span><span class="sxs-lookup"><span data-stu-id="3c79a-188">Actions on users</span></span>
<span data-ttu-id="3c79a-189">Cuando se selecciona, la acción Marcar **al usuario como** comprometida se toma en los usuarios de la columna , o de los `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="3c79a-189">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="3c79a-190">Esta acción establece el nivel de riesgo de los usuarios en "alto" en Azure Active Directory, desencadenando las directivas [de protección de identidades correspondientes.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="3c79a-190">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="3c79a-191">La acción permitir o bloquear para reglas de detección personalizadas actualmente no se admite en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3c79a-191">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="3c79a-192">5. Establezca el ámbito de regla.</span><span class="sxs-lookup"><span data-stu-id="3c79a-192">5. Set the rule scope.</span></span>
<span data-ttu-id="3c79a-193">Establezca el ámbito para especificar los dispositivos cubiertos por la regla.</span><span class="sxs-lookup"><span data-stu-id="3c79a-193">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="3c79a-194">El ámbito influye en las reglas que comprueban los dispositivos y no afectan a las reglas que solo comprueban buzones y cuentas de usuario o identidades.</span><span class="sxs-lookup"><span data-stu-id="3c79a-194">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="3c79a-195">Al establecer el ámbito, puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="3c79a-195">When setting the scope, you can select:</span></span>

- <span data-ttu-id="3c79a-196">Todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="3c79a-196">All devices</span></span>
- <span data-ttu-id="3c79a-197">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="3c79a-197">Specific device groups</span></span>

<span data-ttu-id="3c79a-198">Solo se consultarán los datos de dispositivos en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="3c79a-198">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="3c79a-199">Además, las acciones solo se realizarán en esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3c79a-199">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="3c79a-200">6. Revise y active la regla.</span><span class="sxs-lookup"><span data-stu-id="3c79a-200">6. Review and turn on the rule.</span></span>
<span data-ttu-id="3c79a-201">Después de revisar la regla, seleccione **Crear** para guardarla.</span><span class="sxs-lookup"><span data-stu-id="3c79a-201">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="3c79a-202">La regla de detección personalizada se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="3c79a-202">The custom detection rule immediately runs.</span></span> <span data-ttu-id="3c79a-203">Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y realizar acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3c79a-203">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="3c79a-204">Las detecciones personalizadas deben revisarse periódicamente para obtener eficacia y eficacia.</span><span class="sxs-lookup"><span data-stu-id="3c79a-204">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="3c79a-205">Para asegurarse de que está creando detecciones que desencadenan alertas verdaderas, dedícalse a revisar las detecciones personalizadas existentes siguiendo los pasos descritos en Administrar reglas de detección [personalizadas existentes.](#manage-existing-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="3c79a-205">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="3c79a-206">Se mantiene el control sobre la generalidad o especificidad de las detecciones personalizadas, por lo que cualquier alerta falsa generada por detecciones personalizadas puede indicar la necesidad de modificar determinados parámetros de las reglas.</span><span class="sxs-lookup"><span data-stu-id="3c79a-206">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="3c79a-207">Administrar reglas de detección personalizadas existentes</span><span class="sxs-lookup"><span data-stu-id="3c79a-207">Manage existing custom detection rules</span></span>
<span data-ttu-id="3c79a-208">Puede ver la lista de reglas de detección personalizadas existentes, comprobar sus ejecuciones anteriores y revisar las alertas que han desencadenado.</span><span class="sxs-lookup"><span data-stu-id="3c79a-208">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="3c79a-209">También puede ejecutar una regla a petición y modificarla.</span><span class="sxs-lookup"><span data-stu-id="3c79a-209">You can also run a rule on demand and modify it.</span></span>

>[!TIP]
> <span data-ttu-id="3c79a-210">Las alertas generadas por detecciones personalizadas están disponibles en las API de alertas e incidentes.</span><span class="sxs-lookup"><span data-stu-id="3c79a-210">Alerts raised by custom detections are available over alerts and incident APIs.</span></span> <span data-ttu-id="3c79a-211">Para obtener más información, vea [Supported Microsoft 365 Defender API](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="3c79a-211">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="3c79a-212">Ver reglas existentes</span><span class="sxs-lookup"><span data-stu-id="3c79a-212">View existing rules</span></span>

<span data-ttu-id="3c79a-213">Para ver todas las reglas de detección personalizadas existentes, vaya a **Buscar**  >  **detecciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="3c79a-213">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="3c79a-214">La página enumera todas las reglas con la siguiente información de ejecución:</span><span class="sxs-lookup"><span data-stu-id="3c79a-214">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="3c79a-215">**Última ejecución:** cuando se ejecuta por última vez una regla para comprobar si hay coincidencias de consulta y generar alertas</span><span class="sxs-lookup"><span data-stu-id="3c79a-215">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="3c79a-216">**Estado de la última ejecución:** si una regla se ejecutó correctamente</span><span class="sxs-lookup"><span data-stu-id="3c79a-216">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="3c79a-217">**Siguiente ejecución**: la siguiente ejecución programada</span><span class="sxs-lookup"><span data-stu-id="3c79a-217">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="3c79a-218">**Estado:** si se ha activado o desactivado una regla</span><span class="sxs-lookup"><span data-stu-id="3c79a-218">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="3c79a-219">Ver detalles de regla, modificar regla y ejecutar regla</span><span class="sxs-lookup"><span data-stu-id="3c79a-219">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="3c79a-220">Para ver información completa acerca de una regla de detección personalizada, vaya a **Buscar** detecciones personalizadas y, a continuación,  >   seleccione el nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="3c79a-220">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="3c79a-221">A continuación, puede ver información general sobre la regla, incluida la información sobre su estado de ejecución y su ámbito.</span><span class="sxs-lookup"><span data-stu-id="3c79a-221">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="3c79a-222">La página también proporciona la lista de alertas y acciones desencadenadas.</span><span class="sxs-lookup"><span data-stu-id="3c79a-222">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="3c79a-223">![Página de detalles de regla de detección personalizada](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="3c79a-223">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="3c79a-224">*Detalles de la regla de detección personalizada*</span><span class="sxs-lookup"><span data-stu-id="3c79a-224">*Custom detection rule details*</span></span>

<span data-ttu-id="3c79a-225">También puede realizar las siguientes acciones en la regla desde esta página:</span><span class="sxs-lookup"><span data-stu-id="3c79a-225">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="3c79a-226">**Ejecutar**: ejecute la regla inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="3c79a-226">**Run**—run the rule immediately.</span></span> <span data-ttu-id="3c79a-227">Esto también restablece el intervalo de la siguiente ejecución.</span><span class="sxs-lookup"><span data-stu-id="3c79a-227">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="3c79a-228">**Editar**: modificar la regla sin cambiar la consulta</span><span class="sxs-lookup"><span data-stu-id="3c79a-228">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="3c79a-229">**Modificar consulta**: editar la consulta en búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3c79a-229">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="3c79a-230">**Activar**  /  **Desactivar :** habilitar la regla o impedir que se ejecute</span><span class="sxs-lookup"><span data-stu-id="3c79a-230">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="3c79a-231">**Eliminar**: desactivar la regla y quitarla</span><span class="sxs-lookup"><span data-stu-id="3c79a-231">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="3c79a-232">Ver y administrar alertas desencadenadas</span><span class="sxs-lookup"><span data-stu-id="3c79a-232">View and manage triggered alerts</span></span>

<span data-ttu-id="3c79a-233">En la pantalla de detalles de la regla (**Buscar** detecciones personalizadas [Nombre de regla] ), vaya a Alertas desencadenadas , que enumera las alertas generadas por  >  **coincidencias**  >  con la regla. </span><span class="sxs-lookup"><span data-stu-id="3c79a-233">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="3c79a-234">Seleccione una alerta para ver información detallada al respecto y realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3c79a-234">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="3c79a-235">Administrar la alerta estableciendo su estado y clasificación (alerta verdadera o falsa)</span><span class="sxs-lookup"><span data-stu-id="3c79a-235">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="3c79a-236">Vincular la alerta a un incidente</span><span class="sxs-lookup"><span data-stu-id="3c79a-236">Link the alert to an incident</span></span>
- <span data-ttu-id="3c79a-237">Ejecutar la consulta que desencadenó la alerta en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3c79a-237">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="3c79a-238">Revisar acciones</span><span class="sxs-lookup"><span data-stu-id="3c79a-238">Review actions</span></span>
<span data-ttu-id="3c79a-239">En la pantalla de detalles de la regla (**Buscar** detecciones personalizadas [Nombre de regla] ), vaya a Acciones desencadenadas , que enumera las acciones realizadas en función de las  >  **coincidencias**  >  con la regla. </span><span class="sxs-lookup"><span data-stu-id="3c79a-239">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="3c79a-240">Para ver rápidamente la información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3c79a-240">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

>[!NOTE]
><span data-ttu-id="3c79a-241">Es posible que algunas columnas de este artículo no estén disponibles en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="3c79a-241">Some columns in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3c79a-242">[Activa Microsoft 365 Defender para](m365d-enable.md) buscar amenazas con más orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="3c79a-242">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="3c79a-243">Puede mover los flujos de trabajo avanzados de búsqueda de Microsoft Defender para endpoint a Microsoft 365 Defender siguiendo los pasos descritos en Migrar consultas avanzadas de búsqueda desde [Microsoft Defender para endpoint](advanced-hunting-migrate-from-mde.md).</span><span class="sxs-lookup"><span data-stu-id="3c79a-243">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c79a-244">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c79a-244">See also</span></span>
- [<span data-ttu-id="3c79a-245">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="3c79a-245">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="3c79a-246">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="3c79a-246">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3c79a-247">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3c79a-247">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3c79a-248">Migrar consultas de búsqueda avanzada desde Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="3c79a-248">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
