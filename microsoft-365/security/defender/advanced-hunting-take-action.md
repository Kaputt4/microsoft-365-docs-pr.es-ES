---
title: Realizar acciones en resultados de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Abordar rápidamente las amenazas y los activos afectados en los resultados avanzados de la consulta de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, tomar medidas
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
ms.openlocfilehash: ee35bcc29ef8a283b6b04cb34ab97705d5dd15f4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498224"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="c2edc-104">Realizar acciones en los resultados avanzados de la consulta de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c2edc-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c2edc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c2edc-105">**Applies to:**</span></span>
- <span data-ttu-id="c2edc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2edc-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c2edc-107">Puede contener rápidamente amenazas o solucionar activos en peligro que encuentre en la búsqueda avanzada [mediante](advanced-hunting-overview.md) opciones de acción eficaces y completas.</span><span class="sxs-lookup"><span data-stu-id="c2edc-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="c2edc-108">Con estas opciones, puede:</span><span class="sxs-lookup"><span data-stu-id="c2edc-108">With these options, you can:</span></span>

- <span data-ttu-id="c2edc-109">Realizar varias acciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="c2edc-109">Take various actions on devices</span></span>
- <span data-ttu-id="c2edc-110">Archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="c2edc-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="c2edc-111">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="c2edc-111">Required permissions</span></span>
<span data-ttu-id="c2edc-112">Para poder tomar medidas a través de la búsqueda avanzada, necesita un rol en Microsoft Defender para Endpoint con permisos para enviar acciones de corrección [en dispositivos](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="c2edc-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="c2edc-113">Si no puede tomar medidas, póngase en contacto con un administrador global para obtener el siguiente permiso:</span><span class="sxs-lookup"><span data-stu-id="c2edc-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="c2edc-114">*Acciones de corrección activas > administración de amenazas y vulnerabilidades: control de corrección*</span><span class="sxs-lookup"><span data-stu-id="c2edc-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="c2edc-115">Realizar varias acciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="c2edc-115">Take various actions on devices</span></span>
<span data-ttu-id="c2edc-116">Puede realizar las siguientes acciones en dispositivos identificados por la `DeviceId` columna en los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="c2edc-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="c2edc-117">Aislar dispositivos afectados para contener una infección o evitar que los ataques se muevan lateralmente</span><span class="sxs-lookup"><span data-stu-id="c2edc-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="c2edc-118">Recopilar paquete de investigación para obtener más información forense</span><span class="sxs-lookup"><span data-stu-id="c2edc-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="c2edc-119">Ejecutar un examen antivirus para buscar y eliminar amenazas con las últimas actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="c2edc-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="c2edc-120">Iniciar una investigación automatizada para comprobar y corregir las amenazas en el dispositivo y posiblemente otros dispositivos afectados</span><span class="sxs-lookup"><span data-stu-id="c2edc-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="c2edc-121">Restringir la ejecución de aplicaciones solo a archivos ejecutables firmados por Microsoft, lo que impide la actividad de amenaza posterior a través de malware u otros ejecutables que no son de confianza</span><span class="sxs-lookup"><span data-stu-id="c2edc-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="c2edc-122">Para obtener más información sobre cómo se realizan estas acciones de respuesta a través de Microsoft Defender para endpoint, lea acerca de las [acciones de respuesta en dispositivos](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="c2edc-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="c2edc-123">Archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="c2edc-123">Quarantine files</span></span>
<span data-ttu-id="c2edc-124">Puede implementar la acción *de cuarentena* en los archivos para que se pongan automáticamente en cuarentena cuando se encuentren.</span><span class="sxs-lookup"><span data-stu-id="c2edc-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="c2edc-125">Al seleccionar esta acción, puede elegir entre las siguientes columnas para identificar qué archivos de los resultados de la consulta se ponen en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="c2edc-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="c2edc-126">`SHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el SHA-1 del archivo que se vio afectado por la acción grabada.</span><span class="sxs-lookup"><span data-stu-id="c2edc-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="c2edc-127">Por ejemplo, si se copia un archivo, este sería el archivo copiado.</span><span class="sxs-lookup"><span data-stu-id="c2edc-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="c2edc-128">`InitiatingProcessSHA1` — En la mayoría de las tablas de búsqueda avanzadas, este es el archivo responsable de iniciar la acción grabada.</span><span class="sxs-lookup"><span data-stu-id="c2edc-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="c2edc-129">Por ejemplo, si se inicia un proceso secundario, este sería el proceso primario.</span><span class="sxs-lookup"><span data-stu-id="c2edc-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="c2edc-130">`SHA256` — Este es el equivalente SHA-256 del archivo identificado por la `SHA1` columna.</span><span class="sxs-lookup"><span data-stu-id="c2edc-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="c2edc-131">`InitiatingProcessSHA256` — Este es el equivalente SHA-256 del archivo identificado por la `InitiatingProcessSHA1` columna.</span><span class="sxs-lookup"><span data-stu-id="c2edc-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="c2edc-132">Para obtener más información sobre cómo se toman las acciones de cuarentena y cómo se pueden restaurar los archivos, lea acerca de las [acciones de respuesta en los archivos](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="c2edc-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="c2edc-133">Para buscar archivos y ponerlos en cuarentena, los resultados de la consulta también deben incluir `DeviceId` valores como identificadores de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2edc-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="c2edc-134">Tomar medidas</span><span class="sxs-lookup"><span data-stu-id="c2edc-134">Take action</span></span>
<span data-ttu-id="c2edc-135">Para realizar cualquiera de las acciones descritas, seleccione uno o más registros en los resultados de la consulta y, a continuación, **seleccione Realizar acciones**.</span><span class="sxs-lookup"><span data-stu-id="c2edc-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="c2edc-136">Un asistente le guiará a través del proceso de selección y envío de las acciones preferidas.</span><span class="sxs-lookup"><span data-stu-id="c2edc-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Imagen del registro seleccionado con panel para inspeccionar el registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="c2edc-138">Revisar acciones realizadas</span><span class="sxs-lookup"><span data-stu-id="c2edc-138">Review actions taken</span></span>
<span data-ttu-id="c2edc-139">Cada acción se registra individualmente en el centro [de acciones](m365d-action-center.md) en Historial **del centro** de acciones (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="c2edc-139">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="c2edc-140">Vaya al centro de acciones para comprobar el estado de cada acción.</span><span class="sxs-lookup"><span data-stu-id="c2edc-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="c2edc-141">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c2edc-141">Related topics</span></span>
- [<span data-ttu-id="c2edc-142">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="c2edc-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c2edc-143">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="c2edc-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c2edc-144">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="c2edc-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="c2edc-145">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="c2edc-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c2edc-146">Introducción al Centro de acciones</span><span class="sxs-lookup"><span data-stu-id="c2edc-146">Action center overview</span></span>](m365d-action-center.md)
