---
title: Creación y administración de reglas de detección personalizadas en protección contra amenazas de Microsoft
description: Obtenga información sobre cómo crear y administrar reglas de detección personalizadas basadas en consultas de búsqueda avanzada.
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, reglas, esquema, kusto, Microsoft 365, protección contra amenazas de Microsoft, RBAC, permisos, Microsoft NNC de defender
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: adb8c7dfa0050ef2eb0d59e1e55d07da7aaa3f39
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931757"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="a8f3b-104">Creación y administración de reglas de detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="a8f3b-104">Create and manage custom detections rules</span></span>

<span data-ttu-id="a8f3b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a8f3b-105">**Applies to:**</span></span>
- <span data-ttu-id="a8f3b-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8f3b-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a8f3b-107">Las reglas de detección personalizadas creadas a partir de consultas de [caza avanzadas](advanced-hunting-overview.md) le permiten supervisar de forma proactiva varios eventos y Estados del sistema, como la actividad de infracciones y los extremos configurados incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-107">Custom detection rules built from [Advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="a8f3b-108">Puede establecer que se ejecuten a intervalos regulares, generando alertas y realizando acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-108">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="a8f3b-109">Permisos necesarios para administrar detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="a8f3b-109">Required permissions for managing custom detections</span></span>

<span data-ttu-id="a8f3b-110">Para administrar las detecciones personalizadas, debe tener asignado uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-110">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="a8f3b-111">**Administrador** de seguridad: el rol de administrador de seguridad o administrador de seguridad es un [rol de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) para administrar varias configuraciones de seguridad en el centro de seguridad de Microsoft 365 y varios portales y servicios.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-111">**Security administrator** — the security administrator or security admin role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing various security settings in Microsoft 365 security center and various portals and services.</span></span>

- <span data-ttu-id="a8f3b-112">**Operador de seguridad** : el rol de operador de seguridad es un [rol de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) para administrar alertas y tiene acceso global de solo lectura en características relacionadas con la seguridad, incluida toda la información en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-112">**Security operator** —  the security operator role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing alerts and has global read-only access on security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="a8f3b-113">Este rol es suficiente para administrar detecciones personalizadas solo si el control de acceso basado en roles (RBAC) está desactivado en ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-113">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="a8f3b-114">Si tiene configurado un RBAC, también necesitará el permiso **administrar la configuración de seguridad** para ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-114">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="a8f3b-115">Para administrar los permisos necesarios, un **administrador global** puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-115">To manage required permissions, a **global administrator** can do the following:</span></span>

- <span data-ttu-id="a8f3b-116">Asigne el rol de **Administrador** de seguridad o **operador de seguridad** en el centro de administración de [Microsoft 365](https://admin.microsoft.com/) en **funciones** > **Administrador de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-116">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="a8f3b-117">Compruebe la configuración de RBAC para Microsoft defender ATP en el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/) en **configuración** > **Permissions** > **roles**de permisos.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-117">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="a8f3b-118">Seleccione el rol correspondiente para asignar el permiso **administrar la configuración de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="a8f3b-118">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="a8f3b-119">Para administrar las detecciones personalizadas, los **operadores de seguridad** necesitarán el permiso administrar la **configuración de seguridad** en ATP de Microsoft defender si RBAC está activado.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-119">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="a8f3b-120">Crear una regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="a8f3b-120">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="a8f3b-121">1. Prepare la consulta.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-121">1. Prepare the query.</span></span>

<span data-ttu-id="a8f3b-122">En el centro de seguridad de Microsoft 365, vaya a **búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-122">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="a8f3b-123">Cuando use una consulta nueva, ejecute la consulta para identificar los errores y comprender los posibles resultados.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-123">When using a new query, run the query to identify errors and understand possible results.</span></span>

#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="a8f3b-124">Columnas necesarias en los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="a8f3b-124">Required columns in the query results</span></span>
<span data-ttu-id="a8f3b-125">Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-125">To create a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- <span data-ttu-id="a8f3b-126">Una de las siguientes columnas de dispositivo, usuario o buzón de correo:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-126">One of the following device, user, or mailbox columns:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="a8f3b-127">`SenderFromAddress`(remitente del sobre o dirección de ruta de regreso)</span><span class="sxs-lookup"><span data-stu-id="a8f3b-127">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="a8f3b-128">`SenderMailFromAddress`(dirección del remitente mostrada por el cliente de correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="a8f3b-128">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountSid`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
><span data-ttu-id="a8f3b-129">Se agregará compatibilidad con entidades adicionales a medida que se agreguen nuevas tablas al [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a8f3b-129">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="a8f3b-130">Las consultas sencillas, como las que no usan el `project` operador `summarize` or para personalizar o agregar resultados, normalmente devuelven estas columnas comunes.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-130">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="a8f3b-131">Hay varias formas de garantizar que las consultas más complejas devuelven estas columnas.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-131">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="a8f3b-132">Por ejemplo, si prefiere agregar y contar por entidad en una columna como `DeviceId`, puede volver `Timestamp` a obtenerlo del evento más reciente que implique a cada único. `DeviceId`</span><span class="sxs-lookup"><span data-stu-id="a8f3b-132">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="a8f3b-133">La consulta de ejemplo siguiente cuenta el número de equipos únicos`DeviceId`() con detecciones de antivirus y usa este recuento para buscar solo los equipos con más de cinco detecciones.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-133">The sample query below counts the number of unique machines (`DeviceId`) with antivirus detections and uses this count to find only the machines with more than five detections.</span></span> <span data-ttu-id="a8f3b-134">Para devolver la última `Timestamp`, se usa el `summarize` operador con la `arg_max` función.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-134">To return the latest `Timestamp`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="a8f3b-135">2. cree una nueva regla y proporcione los detalles de la alerta.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-135">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="a8f3b-136">Con la consulta en el editor de consultas, seleccione **crear regla de detección** y especifique los siguientes detalles de alerta:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-136">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="a8f3b-137">**Nombre de detección** : nombre de la regla de detección</span><span class="sxs-lookup"><span data-stu-id="a8f3b-137">**Detection name** — name of the detection rule</span></span>
- <span data-ttu-id="a8f3b-138">**Frecuencia** : intervalo para ejecutar la consulta y realizar una acción.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-138">**Frequency** — interval for running the query and taking action.</span></span> [<span data-ttu-id="a8f3b-139">Consulte más información a continuación</span><span class="sxs-lookup"><span data-stu-id="a8f3b-139">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="a8f3b-140">**Título** de la alerta: título que se muestra con alertas desencadenadas por la regla</span><span class="sxs-lookup"><span data-stu-id="a8f3b-140">**Alert title** — title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="a8f3b-141">**Gravedad** : riesgo potencial del componente o actividad identificados por la regla</span><span class="sxs-lookup"><span data-stu-id="a8f3b-141">**Severity** — potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="a8f3b-142">**Categoría** : componente de amenaza o actividad identificada por la regla</span><span class="sxs-lookup"><span data-stu-id="a8f3b-142">**Category** — threat component or activity identified by the rule</span></span>
- <span data-ttu-id="a8f3b-143">**Mitre att&CK** : una o varias técnicas de ataque identificadas por la regla según se documenta en el [marco de MITRE de ATT&CK](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="a8f3b-143">**MITRE ATT&CK techniques** — one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/)</span></span>
- <span data-ttu-id="a8f3b-144">**Descripción** : más información sobre el componente o la actividad identificados por la regla</span><span class="sxs-lookup"><span data-stu-id="a8f3b-144">**Description** — more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="a8f3b-145">**Acciones recomendadas** : acciones adicionales que los respondedores pueden llevar a cabo en respuesta a una alerta</span><span class="sxs-lookup"><span data-stu-id="a8f3b-145">**Recommended actions** — additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="a8f3b-146">Frecuencia de la regla</span><span class="sxs-lookup"><span data-stu-id="a8f3b-146">Rule frequency</span></span>
<span data-ttu-id="a8f3b-147">Cuando se guarda, una regla de detección personalizada nueva o editada se ejecuta inmediatamente y comprueba si hay coincidencias de los últimos 30 días de datos.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-147">When saved, a new or edited custom detection rule immediately runs and checks for matches from  the past 30 days of data.</span></span> <span data-ttu-id="a8f3b-148">A continuación, la regla se ejecuta de nuevo a intervalos fijos y las duraciones de lookback en función de la frecuencia elegida:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-148">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="a8f3b-149">**Cada 24 horas** : se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días</span><span class="sxs-lookup"><span data-stu-id="a8f3b-149">**Every 24 hours** — runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="a8f3b-150">**Cada 12 horas** : se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="a8f3b-150">**Every 12 hours** — runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="a8f3b-151">**Cada 3 horas** : se ejecuta cada 3 horas y comprueba los datos de las últimas 6 horas.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-151">**Every 3 hours** — runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="a8f3b-152">**Cada hora** : se ejecuta cada hora y se comprueban los datos de las últimas dos horas</span><span class="sxs-lookup"><span data-stu-id="a8f3b-152">**Every hour** — runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="a8f3b-153">Seleccione la frecuencia que coincida con el grado en el que desea supervisar las detecciones y considere la capacidad de su organización para responder a las alertas.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-153">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="a8f3b-154">3. Elija las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-154">3. Choose the impacted entities.</span></span>
<span data-ttu-id="a8f3b-155">Identifique las columnas de los resultados de la consulta en las que espera buscar la entidad afectada principal o afectada.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-155">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="a8f3b-156">Por ejemplo, una consulta puede devolver direcciones de remitente`SenderFromAddress` ( `SenderMailFromAddress`o) y destinatario`RecipientEmailAddress`().</span><span class="sxs-lookup"><span data-stu-id="a8f3b-156">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="a8f3b-157">La identificación de las columnas que representan la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta objetivo.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-157">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="a8f3b-158">Puede seleccionar solo una columna para cada tipo de entidad (buzón, usuario o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="a8f3b-158">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="a8f3b-159">No se pueden seleccionar las columnas que no se devuelven mediante la consulta.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-159">Columns that are not returned by your query can't be selected.</span></span>

### <a name="3-specify-actions-on-files-or-machines"></a><span data-ttu-id="a8f3b-160">3. especificar acciones en archivos o máquinas.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-160">3. Specify actions on files or machines.</span></span>
<span data-ttu-id="a8f3b-161">La regla de detección personalizada puede realizar acciones de forma automática en los archivos o equipos devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-161">Your custom detection rule can automatically take actions on files or machines that are returned by the query.</span></span>

#### <a name="actions-on-machines"></a><span data-ttu-id="a8f3b-162">Acciones en los equipos</span><span class="sxs-lookup"><span data-stu-id="a8f3b-162">Actions on machines</span></span>
<span data-ttu-id="a8f3b-163">Estas acciones se aplican a las máquinas `DeviceId` de la columna de los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-163">These actions are applied to machines in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="a8f3b-164">**Aislar equipo** : usa ATP de Microsoft defender para aplicar el aislamiento de red completo, lo que impide que el equipo se conecte a cualquier aplicación o servicio.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-164">**Isolate machine** — uses Microsoft Defender ATP to apply full network isolation, preventing the machine from connecting to any application or service.</span></span> [<span data-ttu-id="a8f3b-165">Más información acerca del aislamiento de máquina ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="a8f3b-165">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- <span data-ttu-id="a8f3b-166">**Collect Investigation Package** : recopila información del equipo en un archivo zip.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-166">**Collect investigation package** — collects machine information in a ZIP file.</span></span> [<span data-ttu-id="a8f3b-167">Más información sobre el paquete de investigación ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="a8f3b-167">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- <span data-ttu-id="a8f3b-168">**Ejecutar el análisis de antivirus** : realiza un examen completo del antivirus de Windows Defender en el equipo</span><span class="sxs-lookup"><span data-stu-id="a8f3b-168">**Run antivirus scan** — performs a full Windows Defender Antivirus scan on the machine</span></span>
- <span data-ttu-id="a8f3b-169">**Iniciar investigación** : inicia una [investigación automatizada](mtp-autoir.md) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-169">**Initiate investigation** — initiates an [automated investigation](mtp-autoir.md) on the machine</span></span>

#### <a name="actions-on-files"></a><span data-ttu-id="a8f3b-170">Acciones en archivos</span><span class="sxs-lookup"><span data-stu-id="a8f3b-170">Actions on files</span></span>
<span data-ttu-id="a8f3b-171">Cuando se selecciona, la acción de **archivo en cuarentena** se lleva a `SHA1`cabo `InitiatingProcessSHA1`en `SHA256`los archivos `InitiatingProcessSHA256` de la columna,, o de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-171">When selected, the **Quarantine file** action is taken on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="a8f3b-172">Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-172">This action deletes the file from its current location and places a copy in quarantine.</span></span>

> [!NOTE]
> <span data-ttu-id="a8f3b-173">La acción permitir o bloquear para reglas de detección personalizadas no es compatible actualmente con la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-173">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="4-set-the-rule-scope"></a><span data-ttu-id="a8f3b-174">4. establezca el ámbito de la regla.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-174">4. Set the rule scope.</span></span>
<span data-ttu-id="a8f3b-175">Establezca el ámbito para especificar los dispositivos que cubre la regla.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-175">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="a8f3b-176">El ámbito influye en las reglas que comprueban los dispositivos y no afectan a las reglas que solo comprueban buzones de correo y cuentas de usuario o identidades.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-176">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="a8f3b-177">Al establecer el ámbito, puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-177">When setting the scope, you can select:</span></span>

- <span data-ttu-id="a8f3b-178">Todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="a8f3b-178">All devices</span></span>
- <span data-ttu-id="a8f3b-179">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="a8f3b-179">Specific device groups</span></span>

<span data-ttu-id="a8f3b-180">Solo se consultarán los datos de los dispositivos en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-180">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="a8f3b-181">Además, las acciones solo se realizarán en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-181">Also, actions will be taken only on those devices.</span></span>

### <a name="5-review-and-turn-on-the-rule"></a><span data-ttu-id="a8f3b-182">5. Revise y active la regla.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-182">5. Review and turn on the rule.</span></span>
<span data-ttu-id="a8f3b-183">Después de revisar la regla, haga clic en **crear** para guardarla.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-183">After reviewing the rule, click **Create** to save it.</span></span> <span data-ttu-id="a8f3b-184">La regla de detección personalizada se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-184">The custom detection rule immediately runs.</span></span> <span data-ttu-id="a8f3b-185">Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y tomar acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-185">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="a8f3b-186">Administración de reglas de detección personalizadas existentes</span><span class="sxs-lookup"><span data-stu-id="a8f3b-186">Manage existing custom detection rules</span></span>
<span data-ttu-id="a8f3b-187">Puede ver la lista de reglas de detección personalizadas existentes, comprobar las ejecuciones anteriores y revisar las alertas que han desencadenado.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-187">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="a8f3b-188">También puede ejecutar una regla según demanda y modificarla.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-188">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="a8f3b-189">Ver las reglas existentes</span><span class="sxs-lookup"><span data-stu-id="a8f3b-189">View existing rules</span></span>

<span data-ttu-id="a8f3b-190">Para ver todas las reglas de detección personalizadas existentes, vaya a **búsqueda** > de**detecciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-190">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="a8f3b-191">La página enumera todas las reglas con la siguiente información de ejecución:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-191">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="a8f3b-192">**Última ejecución** : cuando se ejecutó una regla por última vez para buscar coincidencias de consulta y generar alertas</span><span class="sxs-lookup"><span data-stu-id="a8f3b-192">**Last run** — when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="a8f3b-193">**Último estado de ejecución** : Si una regla se ejecutó correctamente</span><span class="sxs-lookup"><span data-stu-id="a8f3b-193">**Last run status** — whether a rule ran successfully</span></span>
- <span data-ttu-id="a8f3b-194">**Próxima ejecución** : la siguiente ejecución programada</span><span class="sxs-lookup"><span data-stu-id="a8f3b-194">**Next run** — the next scheduled run</span></span>
- <span data-ttu-id="a8f3b-195">**Estado** : Si una regla se ha activado o desactivado</span><span class="sxs-lookup"><span data-stu-id="a8f3b-195">**Status** — whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="a8f3b-196">Ver detalles de la regla, modificar regla y ejecutar regla</span><span class="sxs-lookup"><span data-stu-id="a8f3b-196">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="a8f3b-197">Para ver información completa acerca de una regla de detección personalizada, seleccione el nombre de la regla de la lista de reglas en la **caza** > de**detecciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-197">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="a8f3b-198">Se abrirá una página sobre la regla de detección personalizada con información general sobre la regla, incluidos los detalles de la alerta, el estado de ejecución y el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-198">This opens a page about the custom detection rule with general information about the rule, including the details of the alert, run status, and scope.</span></span> <span data-ttu-id="a8f3b-199">También proporciona la lista de alertas desencadenadas y desencadenadas.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-199">It also provides the list of triggered alerts and triggered actions.</span></span>

<span data-ttu-id="a8f3b-200">![Página de detalles de la regla de detección personalizada](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="a8f3b-200">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="a8f3b-201">*Detalles de la regla de detección personalizada*</span><span class="sxs-lookup"><span data-stu-id="a8f3b-201">*Custom detection rule details*</span></span>

<span data-ttu-id="a8f3b-202">También puede llevar a cabo las siguientes acciones en la regla de esta página:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-202">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="a8f3b-203">**Ejecutar** : ejecute la regla inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-203">**Run** — run the rule immediately.</span></span> <span data-ttu-id="a8f3b-204">Esto también restablece el intervalo para la siguiente ejecución.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-204">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="a8f3b-205">**Editar** : modificar la regla sin cambiar la consulta</span><span class="sxs-lookup"><span data-stu-id="a8f3b-205">**Edit** — modify the rule without changing the query</span></span>
- <span data-ttu-id="a8f3b-206">**Modificar consulta** : editar la consulta en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="a8f3b-206">**Modify query** — edit the query in advanced hunting</span></span>
- <span data-ttu-id="a8f3b-207">**Activar**desactivar: habilitar la regla o dejar que se ejecute**Turn off**  / </span><span class="sxs-lookup"><span data-stu-id="a8f3b-207">**Turn on** / **Turn off** — enable the rule or stop it from running</span></span>
- <span data-ttu-id="a8f3b-208">**Eliminar** : Desactive la regla y quítela</span><span class="sxs-lookup"><span data-stu-id="a8f3b-208">**Delete** — turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="a8f3b-209">Ver y administrar las alertas desencadenadas</span><span class="sxs-lookup"><span data-stu-id="a8f3b-209">View and manage triggered alerts</span></span>

<span data-ttu-id="a8f3b-210">En la pantalla detalles de la regla (**búsqueda** > **detecciones** > personalizadas **[nombre de la regla]**), vaya a **alertas desencadenadas** para ver la lista de alertas generadas por las coincidencias de la regla.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-210">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered alerts** to view the list of alerts generated by matches to the rule.</span></span> <span data-ttu-id="a8f3b-211">Seleccione una alerta para ver información detallada sobre la misma y lleve a cabo las siguientes acciones en dicha alerta:</span><span class="sxs-lookup"><span data-stu-id="a8f3b-211">Select an alert to view detailed information about that alert and take the following actions on that alert:</span></span>

- <span data-ttu-id="a8f3b-212">Administrar la alerta estableciendo su estado y clasificación (true o false Alert)</span><span class="sxs-lookup"><span data-stu-id="a8f3b-212">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="a8f3b-213">Vincular la alerta a un incidente</span><span class="sxs-lookup"><span data-stu-id="a8f3b-213">Link the alert to an incident</span></span>
- <span data-ttu-id="a8f3b-214">Ejecutar la consulta que desencadenó la alerta en la caza avanzada</span><span class="sxs-lookup"><span data-stu-id="a8f3b-214">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="a8f3b-215">Revisión de acciones</span><span class="sxs-lookup"><span data-stu-id="a8f3b-215">Review actions</span></span>
<span data-ttu-id="a8f3b-216">En la pantalla detalles de la regla (**búsqueda** > **detecciones** > personalizadas **[nombre de la regla]**), vaya a **acciones desencadenadas** para ver la lista de acciones realizadas en función de las coincidencias en la regla.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-216">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions** to view the list of actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="a8f3b-217">Para ver rápidamente información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a8f3b-217">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="a8f3b-218">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="a8f3b-218">Related topic</span></span>
- [<span data-ttu-id="a8f3b-219">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="a8f3b-219">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="a8f3b-220">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="a8f3b-220">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a8f3b-221">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="a8f3b-221">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
