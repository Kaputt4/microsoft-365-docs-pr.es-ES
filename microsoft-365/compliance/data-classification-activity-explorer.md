---
title: Introducción al explorador de actividad
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El explorador de actividad complementa la funcionalidad de la característica de clasificación de datos permitiéndole ver y filtrar las acciones que los usuarios están realizando en el contenido etiquetado.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114012"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="5243f-103">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="5243f-103">Get started with activity explorer</span></span>

<span data-ttu-id="5243f-104">La [introducción a la](data-classification-overview.md) clasificación de datos y las pestañas del [explorador](data-classification-content-explorer.md) de contenido le dan visibilidad sobre qué contenido se ha detectado y etiquetado, y dónde está ese contenido.</span><span class="sxs-lookup"><span data-stu-id="5243f-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="5243f-105">El explorador de actividad complementa este conjunto de funciones permitiéndole supervisar lo que se lleva a cabo con el contenido de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="5243f-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="5243f-106">El explorador de actividades proporciona una vista histórica de las actividades en el contenido etiquetado.</span><span class="sxs-lookup"><span data-stu-id="5243f-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="5243f-107">La información de actividad se recopila Microsoft 365 registros de auditoría unificados, transformados y puestos a disposición en la interfaz de usuario del explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="5243f-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![Marcador de posición captura de pantalla información general explorador de actividad](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="5243f-109">Hay más de 30 filtros diferentes disponibles, estos son algunos:</span><span class="sxs-lookup"><span data-stu-id="5243f-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="5243f-110">Intervalo de fechas:</span><span class="sxs-lookup"><span data-stu-id="5243f-110">date range</span></span>
- <span data-ttu-id="5243f-111">TIPO DE ACTIVIDAD</span><span class="sxs-lookup"><span data-stu-id="5243f-111">activity type</span></span>
- <span data-ttu-id="5243f-112">Ubicación</span><span class="sxs-lookup"><span data-stu-id="5243f-112">location</span></span>
- <span data-ttu-id="5243f-113">Usuario</span><span class="sxs-lookup"><span data-stu-id="5243f-113">user</span></span>
- <span data-ttu-id="5243f-114">Etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="5243f-114">sensitivity label</span></span>
- <span data-ttu-id="5243f-115">Etiqueta de retención:</span><span class="sxs-lookup"><span data-stu-id="5243f-115">retention label</span></span>
- <span data-ttu-id="5243f-116">ruta de acceso del archivo</span><span class="sxs-lookup"><span data-stu-id="5243f-116">file path</span></span>
- <span data-ttu-id="5243f-117">Directiva DLP</span><span class="sxs-lookup"><span data-stu-id="5243f-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="5243f-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5243f-118">Prerequisites</span></span>

<span data-ttu-id="5243f-119">Todas las cuentas que tengan acceso a la clasificación de datos y la usen deben tener una licencia asignada de una de estas suscripciones:</span><span class="sxs-lookup"><span data-stu-id="5243f-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="5243f-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5243f-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="5243f-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5243f-121">Office 365 (E5)</span></span>
- <span data-ttu-id="5243f-122">Complemento de cumplimiento avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="5243f-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="5243f-123">Complemento de inteligencia de amenazas avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="5243f-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="5243f-124">Gobernanza y protección de la información de Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="5243f-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="5243f-125">Cumplimiento de Microsoft 365 E5/A5 </span><span class="sxs-lookup"><span data-stu-id="5243f-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="5243f-126">Permisos</span><span class="sxs-lookup"><span data-stu-id="5243f-126">Permissions</span></span>

 <span data-ttu-id="5243f-127">Para obtener acceso a la pestaña explorador de actividades, se debe asignar explícitamente la pertenencia a una cuenta en cualquiera de estos grupos de roles o concederla explícitamente.</span><span class="sxs-lookup"><span data-stu-id="5243f-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="5243f-128">**Grupos de roles de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="5243f-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="5243f-129">Administrador global</span><span class="sxs-lookup"><span data-stu-id="5243f-129">Global administrator</span></span>
- <span data-ttu-id="5243f-130">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5243f-130">Compliance administrator</span></span>
- <span data-ttu-id="5243f-131">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="5243f-131">Security administrator</span></span>
- <span data-ttu-id="5243f-132">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5243f-132">Compliance data administrator</span></span>

<span data-ttu-id="5243f-133">**Microsoft 365 roles**</span><span class="sxs-lookup"><span data-stu-id="5243f-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="5243f-134">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5243f-134">Compliance administrator</span></span>
- <span data-ttu-id="5243f-135">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="5243f-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="5243f-136">Tipos de actividad</span><span class="sxs-lookup"><span data-stu-id="5243f-136">Activity types</span></span>

<span data-ttu-id="5243f-137">El explorador de actividades recopila información de actividad de los registros de auditoría en varios orígenes de actividades.</span><span class="sxs-lookup"><span data-stu-id="5243f-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="5243f-138">Para obtener información más detallada sobre qué actividad de etiquetado la convierte en explorador de actividades, vea [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span><span class="sxs-lookup"><span data-stu-id="5243f-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="5243f-139">**Actividades de etiquetas** de confidencialidad y actividades de etiquetado de retención de aplicaciones nativas de Office, complemento de Azure Information Protection, SharePoint Online, Exchange Online (solo etiquetas de confidencialidad) y OneDrive. </span><span class="sxs-lookup"><span data-stu-id="5243f-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="5243f-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5243f-140">Some examples are:</span></span>

- <span data-ttu-id="5243f-141">etiqueta aplicada</span><span class="sxs-lookup"><span data-stu-id="5243f-141">label applied</span></span>
- <span data-ttu-id="5243f-142">etiqueta cambiada (actualizada, degradada o eliminada)</span><span class="sxs-lookup"><span data-stu-id="5243f-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="5243f-143">simulación de etiquetado automático</span><span class="sxs-lookup"><span data-stu-id="5243f-143">auto-labeling simulation</span></span>
- <span data-ttu-id="5243f-144">archivo leído</span><span class="sxs-lookup"><span data-stu-id="5243f-144">file read</span></span> 

<span data-ttu-id="5243f-145">**Escáner de Azure Information Protection (AIP) y clientes AIP**</span><span class="sxs-lookup"><span data-stu-id="5243f-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="5243f-146">protección aplicada</span><span class="sxs-lookup"><span data-stu-id="5243f-146">protection applied</span></span>
- <span data-ttu-id="5243f-147">protección modificada</span><span class="sxs-lookup"><span data-stu-id="5243f-147">protection changed</span></span>
- <span data-ttu-id="5243f-148">protección eliminada</span><span class="sxs-lookup"><span data-stu-id="5243f-148">protection removed</span></span>
- <span data-ttu-id="5243f-149">archivos detectados</span><span class="sxs-lookup"><span data-stu-id="5243f-149">files discovered</span></span> 

<span data-ttu-id="5243f-150">El explorador de actividades también recopila eventos de coincidencias de directivas **DLP** de Exchange Online, SharePoint Online, OneDrive, chat y canal de Teams (versión preliminar), carpetas y bibliotecas de SharePoint locales y recursos compartidos de archivos locales y dispositivos Windows 10 mediante prevención de pérdida de datos de extremo **(DLP).**</span><span class="sxs-lookup"><span data-stu-id="5243f-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="5243f-151">Algunos ejemplos de eventos de Windows 10 dispositivos son archivos:</span><span class="sxs-lookup"><span data-stu-id="5243f-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="5243f-152">eliminaciones</span><span class="sxs-lookup"><span data-stu-id="5243f-152">deletions</span></span>
- <span data-ttu-id="5243f-153">creaciones</span><span class="sxs-lookup"><span data-stu-id="5243f-153">creations</span></span>
- <span data-ttu-id="5243f-154">copiado en el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="5243f-154">copied to clipboard</span></span>
- <span data-ttu-id="5243f-155">modificado </span><span class="sxs-lookup"><span data-stu-id="5243f-155">modified</span></span>
- <span data-ttu-id="5243f-156">read</span><span class="sxs-lookup"><span data-stu-id="5243f-156">read</span></span>
- <span data-ttu-id="5243f-157">impreso</span><span class="sxs-lookup"><span data-stu-id="5243f-157">printed</span></span>
- <span data-ttu-id="5243f-158">nombre cambiado</span><span class="sxs-lookup"><span data-stu-id="5243f-158">renamed</span></span>
- <span data-ttu-id="5243f-159">copiado en el recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="5243f-159">copied to network share</span></span>
- <span data-ttu-id="5243f-160">a la que se accede mediante una aplicación sin alambrar</span><span class="sxs-lookup"><span data-stu-id="5243f-160">accessed by unallowed app</span></span> 

<span data-ttu-id="5243f-161">El valor de comprender qué acciones se están haciendo con el contenido etiquetado confidencial es que puede ver si los controles que ya ha puesto en marcha, como la prevención de pérdida de datos son [efectivos](dlp-learn-about-dlp.md) o no.</span><span class="sxs-lookup"><span data-stu-id="5243f-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="5243f-162">Si no es así, o si se detecta algo inesperado, como un gran número de elementos etiquetados `highly confidential`y se degradan`general`, puede administrar las distintas directivas y llevar a cabo nuevas acciones para restringir el comportamiento no deseado.</span><span class="sxs-lookup"><span data-stu-id="5243f-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="5243f-163">El explorador de actividad no supervisa actualmente las actividades de retención de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5243f-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="5243f-164">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5243f-164">See also</span></span>

- [<span data-ttu-id="5243f-165">Información sobre las etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="5243f-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="5243f-166">Más información sobre las directivas y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="5243f-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="5243f-167">Obtener más información acerca de los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="5243f-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="5243f-168">Obtenga información sobre la clasificación de datos.</span><span class="sxs-lookup"><span data-stu-id="5243f-168">Learn about data classification</span></span>](data-classification-overview.md)
