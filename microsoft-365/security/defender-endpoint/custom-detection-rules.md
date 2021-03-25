---
title: Crear reglas de detección personalizadas en ATP de Microsoft Defender
ms.reviewer: ''
description: Obtenga información sobre cómo crear reglas de detección personalizadas basadas en consultas avanzadas de búsqueda
keywords: detecciones personalizadas, crear, administrar, alertas, editar, ejecutar a petición, frecuencia, intervalo, reglas de detección, búsqueda avanzada, búsqueda, consulta, acciones de respuesta, mdatp, atp de microsoft defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: fc4c15d2e391176ed0b4420c13fb865674da0361
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163592"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="62a9a-104">Crear reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="62a9a-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="62a9a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="62a9a-105">**Applies to:**</span></span>
- [<span data-ttu-id="62a9a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="62a9a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="62a9a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62a9a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="62a9a-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="62a9a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="62a9a-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="62a9a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="62a9a-110">Las reglas de [](advanced-hunting-overview.md) detección personalizadas creadas a partir de consultas avanzadas de búsqueda permiten supervisar proactivamente varios eventos y estados del sistema, incluidos la actividad de infracciones sospechosas y dispositivos mal configurados.</span><span class="sxs-lookup"><span data-stu-id="62a9a-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="62a9a-111">Puede configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="62a9a-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="62a9a-112">Lea este artículo para obtener información sobre cómo crear nuevas reglas de detección personalizadas.</span><span class="sxs-lookup"><span data-stu-id="62a9a-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="62a9a-113">O [vea ver y administrar reglas existentes.](custom-detections-manage.md)</span><span class="sxs-lookup"><span data-stu-id="62a9a-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="62a9a-114">Para crear o administrar detecciones personalizadas, [el rol](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) debe tener el permiso administrar la **configuración de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="62a9a-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="62a9a-115">1. Prepare la consulta.</span><span class="sxs-lookup"><span data-stu-id="62a9a-115">1. Prepare the query.</span></span>

<span data-ttu-id="62a9a-116">En el Centro de seguridad de Microsoft Defender, vaya a **Búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="62a9a-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="62a9a-117">Al usar una nueva consulta, ejecute la consulta para identificar errores y comprender los posibles resultados.</span><span class="sxs-lookup"><span data-stu-id="62a9a-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="62a9a-118">Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar solo 100 alertas cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="62a9a-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="62a9a-119">Antes de crear una regla, ajusta la consulta para evitar alertas de actividad normal del día a día.</span><span class="sxs-lookup"><span data-stu-id="62a9a-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="62a9a-120">Columnas necesarias en los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="62a9a-120">Required columns in the query results</span></span>

<span data-ttu-id="62a9a-121">Para usar una consulta para una regla de detección personalizada, la consulta debe devolver las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="62a9a-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="62a9a-122">Las consultas simples, como las que no usan el operador or para personalizar o agregar resultados, normalmente `project` `summarize` devuelven estas columnas comunes.</span><span class="sxs-lookup"><span data-stu-id="62a9a-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="62a9a-123">Hay varias maneras de garantizar que las consultas más complejas devuelvan estas columnas.</span><span class="sxs-lookup"><span data-stu-id="62a9a-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="62a9a-124">Por ejemplo, si prefieres agregar y contar por , aún puedes devolverlos y obtenerlos del evento más reciente que implica `DeviceId` `Timestamp` cada `ReportId` dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62a9a-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="62a9a-125">La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( ) con detecciones antivirus y lo usa para buscar solo aquellos dispositivos con más `DeviceId` de cinco detecciones.</span><span class="sxs-lookup"><span data-stu-id="62a9a-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="62a9a-126">Para devolver el último `Timestamp` y el correspondiente , usa el operador con la `ReportId` `summarize` `arg_max` función.</span><span class="sxs-lookup"><span data-stu-id="62a9a-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="62a9a-127">Para obtener un mejor rendimiento de consulta, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla.</span><span class="sxs-lookup"><span data-stu-id="62a9a-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="62a9a-128">Dado que la ejecución menos frecuente es cada 24 horas, el filtrado del último día cubrirá todos los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="62a9a-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="62a9a-129">2. Cree una nueva regla y proporcione detalles de alerta.</span><span class="sxs-lookup"><span data-stu-id="62a9a-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="62a9a-130">Con la consulta en el editor de consultas, seleccione **Crear regla de detección** y especifique los siguientes detalles de alerta:</span><span class="sxs-lookup"><span data-stu-id="62a9a-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="62a9a-131">**Nombre de detección**: nombre de la regla de detección</span><span class="sxs-lookup"><span data-stu-id="62a9a-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="62a9a-132">**Frecuencia:** intervalo para ejecutar la consulta y realizar acciones.</span><span class="sxs-lookup"><span data-stu-id="62a9a-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="62a9a-133">Vea instrucciones adicionales a continuación</span><span class="sxs-lookup"><span data-stu-id="62a9a-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="62a9a-134">**Título de alerta:** título que se muestra con alertas desencadenadas por la regla</span><span class="sxs-lookup"><span data-stu-id="62a9a-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="62a9a-135">**Gravedad:** riesgo potencial del componente o actividad identificado por la regla.</span><span class="sxs-lookup"><span data-stu-id="62a9a-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="62a9a-136">Leer sobre gravedades de alerta</span><span class="sxs-lookup"><span data-stu-id="62a9a-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="62a9a-137">**Categoría**: tipo de componente o actividad de amenaza, si la hay.</span><span class="sxs-lookup"><span data-stu-id="62a9a-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="62a9a-138">Leer sobre categorías de alertas</span><span class="sxs-lookup"><span data-stu-id="62a9a-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="62a9a-139">**MITRE ATT&técnicas de CK:** una o más técnicas de ataque identificadas por la regla como se documentan en el marco&CK de MITRE ATT.</span><span class="sxs-lookup"><span data-stu-id="62a9a-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="62a9a-140">Esta sección no está disponible con determinadas categorías de alertas, como malware, ransomware, actividad sospechosa y software no deseado</span><span class="sxs-lookup"><span data-stu-id="62a9a-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="62a9a-141">**Descripción:** más información sobre el componente o la actividad identificada por la regla</span><span class="sxs-lookup"><span data-stu-id="62a9a-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="62a9a-142">**Acciones recomendadas:** acciones adicionales que los respondedores pueden realizar en respuesta a una alerta</span><span class="sxs-lookup"><span data-stu-id="62a9a-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="62a9a-143">Para obtener más información acerca de cómo se muestran los detalles de alerta, [lea acerca de la cola de alertas](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="62a9a-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="62a9a-144">Frecuencia de regla</span><span class="sxs-lookup"><span data-stu-id="62a9a-144">Rule frequency</span></span>

<span data-ttu-id="62a9a-145">Cuando se guarda, una nueva regla de detección personalizada se ejecuta inmediatamente y comprueba las coincidencias de los últimos 30 días de datos.</span><span class="sxs-lookup"><span data-stu-id="62a9a-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="62a9a-146">A continuación, la regla se ejecuta de nuevo a intervalos fijos y duraciones de devolución según la frecuencia que elija:</span><span class="sxs-lookup"><span data-stu-id="62a9a-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="62a9a-147">**Cada 24 horas:** se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días</span><span class="sxs-lookup"><span data-stu-id="62a9a-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="62a9a-148">**Cada 12 horas:** se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="62a9a-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="62a9a-149">**Cada 3 horas:** se ejecuta cada 3 horas, comprobando los datos de las últimas 6 horas</span><span class="sxs-lookup"><span data-stu-id="62a9a-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="62a9a-150">**Cada hora:** se ejecuta cada hora, comprobando los datos de las últimas 2 horas</span><span class="sxs-lookup"><span data-stu-id="62a9a-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62a9a-151">Al cambiar una consulta que ya está programada como detección personalizada, la próxima ejecución inmediata tendrá una ventana de devolución de 30 días, exactamente como si se creara una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="62a9a-151">When changing a query that is already scheduled as a Custom Detection, it's next immediate execution will have a lookback window of 30 days, exactly as if a new query was being created.</span></span> <span data-ttu-id="62a9a-152">Los cambios en un gran número de consultas y con filtros de tiempo superiores a la duración predeterminada de la devolución de la frecuencia seleccionada pueden tener un impacto en el consumo de cuota general de búsqueda avanzada y provocar el agotamiento de la cuota diaria.</span><span class="sxs-lookup"><span data-stu-id="62a9a-152">Changes to a large number of queries, and with time filters higher than the default lookback duration for the selected frequency, might have an impact in the overall quota consumption of Advanced Hunting and resulting in exhausting the daily quota.</span></span>

> [!TIP]
> <span data-ttu-id="62a9a-153">Coincide con los filtros de tiempo de la consulta con la duración de la devolución.</span><span class="sxs-lookup"><span data-stu-id="62a9a-153">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="62a9a-154">Se omiten los resultados fuera de la duración de la devolución.</span><span class="sxs-lookup"><span data-stu-id="62a9a-154">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="62a9a-155">Seleccione la frecuencia que coincida con la frecuencia con la que desea supervisar las detecciones y tenga en cuenta la capacidad de su organización para responder a las alertas.</span><span class="sxs-lookup"><span data-stu-id="62a9a-155">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="62a9a-156">3. Elija las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="62a9a-156">3. Choose the impacted entities.</span></span>

<span data-ttu-id="62a9a-157">Identifique las columnas de los resultados de la consulta en las que espera encontrar la entidad principal afectada o afectada.</span><span class="sxs-lookup"><span data-stu-id="62a9a-157">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="62a9a-158">Por ejemplo, una consulta puede devolver los id. de dispositivo y de usuario.</span><span class="sxs-lookup"><span data-stu-id="62a9a-158">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="62a9a-159">La identificación de cuál de estas columnas representa la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta de destino.</span><span class="sxs-lookup"><span data-stu-id="62a9a-159">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="62a9a-160">Solo puede seleccionar una columna para cada tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="62a9a-160">You can select only one column for each entity type.</span></span> <span data-ttu-id="62a9a-161">Las columnas que la consulta no devuelve no se pueden seleccionar.</span><span class="sxs-lookup"><span data-stu-id="62a9a-161">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="62a9a-162">4. Especifique acciones.</span><span class="sxs-lookup"><span data-stu-id="62a9a-162">4. Specify actions.</span></span>

<span data-ttu-id="62a9a-163">La regla de detección personalizada puede realizar automáticamente acciones en archivos o dispositivos devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="62a9a-163">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="62a9a-164">Acciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="62a9a-164">Actions on devices</span></span>

<span data-ttu-id="62a9a-165">Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="62a9a-165">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="62a9a-166">**Aislar dispositivo:** aplica aislamiento de red completo, lo que impide que el dispositivo se conecte a cualquier aplicación o servicio, excepto para el servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="62a9a-166">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="62a9a-167">Más información sobre el aislamiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="62a9a-167">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="62a9a-168">**Recopilar paquete de investigación:** recopila información del dispositivo en un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="62a9a-168">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="62a9a-169">Más información sobre el paquete de investigación</span><span class="sxs-lookup"><span data-stu-id="62a9a-169">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="62a9a-170">**Ejecutar examen antivirus:** realiza un examen completo de Antivirus de Microsoft Defender en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="62a9a-170">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="62a9a-171">**Iniciar investigación:** inicia una [investigación automatizada](automated-investigations.md) en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="62a9a-171">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="62a9a-172">**Restringir la ejecución de** la aplicación: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos que están firmados con un certificado emitido por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="62a9a-172">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="62a9a-173">Más información sobre cómo restringir la ejecución de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="62a9a-173">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="62a9a-174">Acciones en archivos</span><span class="sxs-lookup"><span data-stu-id="62a9a-174">Actions on files</span></span>

<span data-ttu-id="62a9a-175">Estas acciones se aplican a los archivos de la `SHA1` columna o de los `InitiatingProcessSHA1` resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="62a9a-175">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="62a9a-176">**Allow/Block:** agrega automáticamente el archivo a la lista de [indicadores](manage-indicators.md) personalizados para que siempre pueda ejecutarse o bloquearse para que no se ejecute.</span><span class="sxs-lookup"><span data-stu-id="62a9a-176">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="62a9a-177">Puedes establecer el ámbito de esta acción de modo que solo se haya realizado en grupos de dispositivos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="62a9a-177">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="62a9a-178">Este ámbito es independiente del ámbito de la regla.</span><span class="sxs-lookup"><span data-stu-id="62a9a-178">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="62a9a-179">**Archivo de** cuarentena: elimina el archivo de su ubicación actual y coloca una copia en cuarentena</span><span class="sxs-lookup"><span data-stu-id="62a9a-179">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="62a9a-180">Acciones en usuarios</span><span class="sxs-lookup"><span data-stu-id="62a9a-180">Actions on users</span></span>

- <span data-ttu-id="62a9a-181">**Marcar usuario como comprometido:** establece el nivel de riesgo del usuario en "alto" en Azure Active Directory, desencadenando las directivas de protección de [identidades correspondientes.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)</span><span class="sxs-lookup"><span data-stu-id="62a9a-181">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="62a9a-182">5. Establezca el ámbito de regla.</span><span class="sxs-lookup"><span data-stu-id="62a9a-182">5. Set the rule scope.</span></span>

<span data-ttu-id="62a9a-183">Establezca el ámbito para especificar los dispositivos cubiertos por la regla:</span><span class="sxs-lookup"><span data-stu-id="62a9a-183">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="62a9a-184">Todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="62a9a-184">All devices</span></span>
- <span data-ttu-id="62a9a-185">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="62a9a-185">Specific device groups</span></span>

<span data-ttu-id="62a9a-186">Solo se consultarán los datos de dispositivos en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="62a9a-186">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="62a9a-187">Además, las acciones solo se realizarán en esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="62a9a-187">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="62a9a-188">6. Revise y active la regla.</span><span class="sxs-lookup"><span data-stu-id="62a9a-188">6. Review and turn on the rule.</span></span>

<span data-ttu-id="62a9a-189">Después de revisar la regla, seleccione **Crear** para guardarla.</span><span class="sxs-lookup"><span data-stu-id="62a9a-189">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="62a9a-190">La regla de detección personalizada se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="62a9a-190">The custom detection rule immediately runs.</span></span> <span data-ttu-id="62a9a-191">Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y realizar acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="62a9a-191">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="62a9a-192">Puede ver [y administrar reglas de detección personalizadas,](custom-detections-manage.md)comprobar sus ejecuciones anteriores y revisar las alertas que han desencadenado.</span><span class="sxs-lookup"><span data-stu-id="62a9a-192">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="62a9a-193">También puede ejecutar una regla a petición y modificarla.</span><span class="sxs-lookup"><span data-stu-id="62a9a-193">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="62a9a-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="62a9a-194">Related topics</span></span>

- [<span data-ttu-id="62a9a-195">Ver y administrar reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="62a9a-195">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="62a9a-196">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="62a9a-196">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="62a9a-197">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="62a9a-197">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="62a9a-198">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="62a9a-198">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="62a9a-199">Ver y organizar alertas</span><span class="sxs-lookup"><span data-stu-id="62a9a-199">View and organize alerts</span></span>](alerts-queue.md)
