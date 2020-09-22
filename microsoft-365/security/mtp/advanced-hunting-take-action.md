---
title: Realizar acciones en los resultados de la consulta de búsqueda avanzada en protección contra amenazas de Microsoft
description: Solucionar rápidamente las amenazas y los activos afectados en los resultados de la consulta de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, emprender acciones
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
ms.openlocfilehash: 14785e032d6e4a7a0868308f4029df623456af2a
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197898"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="a5dd9-104">Realizar acciones en los resultados de la consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="a5dd9-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a5dd9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a5dd9-105">**Applies to:**</span></span>
- <span data-ttu-id="a5dd9-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5dd9-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a5dd9-107">Puede contener amenazas o dirigir a los activos en peligro que encuentra en la [búsqueda avanzada](advanced-hunting-overview.md) con opciones de acción potentes y completas.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="a5dd9-108">Con estas opciones, puede:</span><span class="sxs-lookup"><span data-stu-id="a5dd9-108">With these options, you can:</span></span>

- <span data-ttu-id="a5dd9-109">Realizar diversas acciones en los dispositivos</span><span class="sxs-lookup"><span data-stu-id="a5dd9-109">Take various actions on devices</span></span>
- <span data-ttu-id="a5dd9-110">Archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="a5dd9-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="a5dd9-111">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="a5dd9-111">Required permissions</span></span>
<span data-ttu-id="a5dd9-112">Para poder emprender acciones a través de la búsqueda avanzada, necesita un rol en Microsoft defender ATP con [permisos para enviar acciones de corrección en los dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="a5dd9-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender ATP with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="a5dd9-113">Si no puede emprender ninguna acción, póngase en contacto con un administrador global para obtener el siguiente permiso:</span><span class="sxs-lookup"><span data-stu-id="a5dd9-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="a5dd9-114">*Acciones de corrección activas > administración de amenazas y vulnerabilidades-control de correcciones*</span><span class="sxs-lookup"><span data-stu-id="a5dd9-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="a5dd9-115">Realizar diversas acciones en los dispositivos</span><span class="sxs-lookup"><span data-stu-id="a5dd9-115">Take various actions on devices</span></span>
<span data-ttu-id="a5dd9-116">Puede realizar las siguientes acciones en los dispositivos identificados por la `DeviceId` columna de los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="a5dd9-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="a5dd9-117">Aislar los dispositivos afectados para que contengan una infección o impedir que los ataques se muevan con posterioridad</span><span class="sxs-lookup"><span data-stu-id="a5dd9-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="a5dd9-118">Recopilar el paquete de investigación para obtener más información forense</span><span class="sxs-lookup"><span data-stu-id="a5dd9-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="a5dd9-119">Ejecutar un análisis antivirus para buscar y eliminar amenazas con las últimas actualizaciones de inteligencia sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="a5dd9-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="a5dd9-120">Iniciar una investigación automatizada para comprobar y corregir las amenazas en el dispositivo y posiblemente en otros dispositivos afectados</span><span class="sxs-lookup"><span data-stu-id="a5dd9-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="a5dd9-121">Restringir la ejecución de la aplicación solo a archivos ejecutables firmados por Microsoft, evitando actividades posteriores de amenazas a través de malware u otros ejecutables que no son de confianza</span><span class="sxs-lookup"><span data-stu-id="a5dd9-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="a5dd9-122">Para obtener más información sobre cómo estas acciones de respuesta se realizan a través de ATP de Microsoft defender, [Lea acerca de las acciones de respuesta en los dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="a5dd9-122">To learn more about how these response actions are performed through Microsoft Defender ATP, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="a5dd9-123">Archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="a5dd9-123">Quarantine files</span></span>
<span data-ttu-id="a5dd9-124">Puede implementar la acción de *cuarentena* en los archivos para que se pongan en cuarentena automáticamente cuando se detecten.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="a5dd9-125">Al seleccionar esta acción, puede elegir entre las siguientes columnas para identificar los archivos de los resultados de la consulta que se pondrán en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="a5dd9-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="a5dd9-126">`SHA1` (En la mayoría de las tablas de búsqueda avanzadas), es el SHA-1 del archivo que se ha visto afectado por la acción grabada.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="a5dd9-127">Por ejemplo, si se ha copiado un archivo, sería el archivo copiado.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="a5dd9-128">`InitiatingProcessSHA1` (En la mayoría de las tablas de la caza avanzadas), es el archivo responsable de iniciar la acción grabada.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="a5dd9-129">Por ejemplo, si se inició un proceso secundario, sería el proceso principal.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="a5dd9-130">`SHA256` : Es el equivalente de SHA-256 del archivo identificado por la `SHA1` columna.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="a5dd9-131">`InitiatingProcessSHA256` : Es el equivalente de SHA-256 del archivo identificado por la `InitiatingProcessSHA1` columna.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="a5dd9-132">Para obtener más información sobre cómo se llevan a cabo las acciones de cuarentena y cómo se pueden restaurar los archivos, [vea acciones de respuesta en los archivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="a5dd9-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="a5dd9-133">Para buscar archivos y ponerlos en cuarentena, los resultados de la consulta también deben incluir `DeviceId` valores como identificadores de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="a5dd9-134">Emprender acciones</span><span class="sxs-lookup"><span data-stu-id="a5dd9-134">Take action</span></span>
<span data-ttu-id="a5dd9-135">Para realizar cualquiera de las acciones descritas, seleccione uno o más registros en los resultados de la consulta y, a continuación, seleccione **emprender acciones**.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="a5dd9-136">Un asistente le guiará por el proceso de selección y envío de las acciones preferidas.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Imagen del registro seleccionado con panel para inspeccionar el registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="a5dd9-138">Revisión de las acciones realizadas</span><span class="sxs-lookup"><span data-stu-id="a5dd9-138">Review actions taken</span></span>
<span data-ttu-id="a5dd9-139">Cada acción se registra individualmente en el [centro de actividades](mtp-action-center.md) , en historial del **centro de actividades**  >  **History** ([Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="a5dd9-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="a5dd9-140">Vaya al centro de actividades para comprobar el estado de cada acción.</span><span class="sxs-lookup"><span data-stu-id="a5dd9-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="a5dd9-141">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a5dd9-141">Related topics</span></span>
- [<span data-ttu-id="a5dd9-142">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="a5dd9-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a5dd9-143">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="a5dd9-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a5dd9-144">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="a5dd9-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="a5dd9-145">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="a5dd9-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a5dd9-146">Información general del centro de actividades</span><span class="sxs-lookup"><span data-stu-id="a5dd9-146">Action center overview</span></span>](mtp-action-center.md)
