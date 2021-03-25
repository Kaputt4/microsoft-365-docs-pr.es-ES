---
title: Tomar medidas sobre los resultados avanzados de consulta de búsqueda en Microsoft Threat Protection
description: Abordar rápidamente las amenazas y los activos afectados en los resultados avanzados de la consulta de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, telemetría, detecciones personalizadas, esquema, kusto, evitar el tiempo de espera, líneas de comandos, id. de proceso
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
ms.openlocfilehash: 79d720a8b996f826548b79834e5d5c2048e28c2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075451"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="6349e-104">Realizar acciones en los resultados avanzados de la consulta de búsqueda</span><span class="sxs-lookup"><span data-stu-id="6349e-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="6349e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6349e-105">**Applies to:**</span></span>
- [<span data-ttu-id="6349e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6349e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="6349e-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6349e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6349e-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6349e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="6349e-109">Puede contener rápidamente amenazas o solucionar activos en peligro que encuentre en la búsqueda avanzada [mediante](advanced-hunting-overview.md) opciones de acción eficaces y completas.</span><span class="sxs-lookup"><span data-stu-id="6349e-109">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="6349e-110">Con estas opciones, puede:</span><span class="sxs-lookup"><span data-stu-id="6349e-110">With these options, you can:</span></span>

- <span data-ttu-id="6349e-111">Realizar varias acciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="6349e-111">Take various actions on devices</span></span>
- <span data-ttu-id="6349e-112">Archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="6349e-112">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="6349e-113">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="6349e-113">Required permissions</span></span>

<span data-ttu-id="6349e-114">Para poder tomar medidas a través de la búsqueda avanzada, necesita un rol en Defender for Endpoint con permisos para enviar acciones de corrección [en dispositivos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="6349e-114">To be able to take action through advanced hunting, you need a role in Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span></span> <span data-ttu-id="6349e-115">Si no puede tomar medidas, póngase en contacto con un administrador global para obtener el siguiente permiso:</span><span class="sxs-lookup"><span data-stu-id="6349e-115">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="6349e-116">*Acciones de corrección activas > administración de amenazas y vulnerabilidades: control de corrección*</span><span class="sxs-lookup"><span data-stu-id="6349e-116">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="6349e-117">Realizar varias acciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="6349e-117">Take various actions on devices</span></span>

<span data-ttu-id="6349e-118">Puede realizar las siguientes acciones en dispositivos identificados por la `DeviceId` columna en los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="6349e-118">You can take the following actions on devices identified by the `DeviceId` column in your query results:</span></span>

- <span data-ttu-id="6349e-119">Aislar dispositivos afectados para contener una infección o evitar que los ataques se muevan lateralmente</span><span class="sxs-lookup"><span data-stu-id="6349e-119">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="6349e-120">Recopilar paquete de investigación para obtener más información forense</span><span class="sxs-lookup"><span data-stu-id="6349e-120">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="6349e-121">Ejecutar un examen antivirus para buscar y eliminar amenazas con las últimas actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6349e-121">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="6349e-122">Iniciar una investigación automatizada para comprobar y corregir las amenazas en el dispositivo y posiblemente otros dispositivos afectados</span><span class="sxs-lookup"><span data-stu-id="6349e-122">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="6349e-123">Restringir la ejecución de aplicaciones solo a archivos ejecutables firmados por Microsoft, lo que impide la actividad de amenaza posterior a través de malware u otros ejecutables que no son de confianza</span><span class="sxs-lookup"><span data-stu-id="6349e-123">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="6349e-124">Para obtener más información sobre cómo se realizan estas acciones de respuesta a través de Defender for Endpoint, lea sobre las [acciones de respuesta en dispositivos](respond-machine-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="6349e-124">To learn more about how these response actions are performed through Defender for Endpoint, [read about response actions on devices](respond-machine-alerts.md).</span></span>

## <a name="quarantine-files"></a><span data-ttu-id="6349e-125">Archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="6349e-125">Quarantine files</span></span>

<span data-ttu-id="6349e-126">Puede implementar la acción *de cuarentena* en los archivos para que se pongan automáticamente en cuarentena cuando se encuentren.</span><span class="sxs-lookup"><span data-stu-id="6349e-126">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="6349e-127">Al seleccionar esta acción, puede elegir entre las siguientes columnas para identificar qué archivos de los resultados de la consulta se ponen en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="6349e-127">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="6349e-128">`SHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el SHA-1 del archivo que se vio afectado por la acción grabada.</span><span class="sxs-lookup"><span data-stu-id="6349e-128">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="6349e-129">Por ejemplo, si se copia un archivo, este sería el archivo copiado.</span><span class="sxs-lookup"><span data-stu-id="6349e-129">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="6349e-130">`InitiatingProcessSHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el archivo responsable de iniciar la acción grabada.</span><span class="sxs-lookup"><span data-stu-id="6349e-130">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="6349e-131">Por ejemplo, si se inicia un proceso secundario, este sería el proceso primario.</span><span class="sxs-lookup"><span data-stu-id="6349e-131">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="6349e-132">`SHA256` — Este es el equivalente SHA-256 del archivo identificado por la `SHA1` columna.</span><span class="sxs-lookup"><span data-stu-id="6349e-132">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="6349e-133">`InitiatingProcessSHA256` — Este es el equivalente SHA-256 del archivo identificado por la `InitiatingProcessSHA1` columna.</span><span class="sxs-lookup"><span data-stu-id="6349e-133">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="6349e-134">Para obtener más información sobre cómo se toman las acciones de cuarentena y cómo se pueden restaurar los archivos, lea acerca de las [acciones de respuesta en los archivos](respond-file-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="6349e-134">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](respond-file-alerts.md).</span></span>

>[!NOTE]
><span data-ttu-id="6349e-135">Para buscar archivos y ponerlos en cuarentena, los resultados de la consulta también deben incluir `DeviceId` valores como identificadores de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6349e-135">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="6349e-136">Tomar medidas</span><span class="sxs-lookup"><span data-stu-id="6349e-136">Take action</span></span>

<span data-ttu-id="6349e-137">Para realizar cualquiera de las acciones descritas, seleccione uno o más registros en los resultados de la consulta y, a continuación, **seleccione Realizar acciones**.</span><span class="sxs-lookup"><span data-stu-id="6349e-137">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="6349e-138">Un asistente le guiará a través del proceso de selección y envío de las acciones preferidas.</span><span class="sxs-lookup"><span data-stu-id="6349e-138">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Imagen del registro seleccionado con panel para inspeccionar el registro](images/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="6349e-140">Revisar acciones realizadas</span><span class="sxs-lookup"><span data-stu-id="6349e-140">Review actions taken</span></span>

<span data-ttu-id="6349e-141">Cada acción se registra individualmente en el centro de acciones, en **Historial del centro** de acciones (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="6349e-141">Each action is individually recorded in the action center, under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="6349e-142">Vaya al centro de acciones para comprobar el estado de cada acción.</span><span class="sxs-lookup"><span data-stu-id="6349e-142">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="6349e-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6349e-143">Related topics</span></span>

- [<span data-ttu-id="6349e-144">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="6349e-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6349e-145">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="6349e-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6349e-146">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="6349e-146">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="6349e-147">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="6349e-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="6349e-148">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="6349e-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6349e-149">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="6349e-149">Custom detections overview</span></span>](overview-custom-detections.md)
