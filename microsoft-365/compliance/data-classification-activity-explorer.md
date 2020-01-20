---
title: Usar el explorador de actividad de clasificación de datos
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El explorador de actividad complementa la funcionalidad de la característica de clasificación de datos permitiéndole ver y filtrar las acciones que los usuarios están realizando en el contenido etiquetado.
ms.openlocfilehash: ab80de0e1be3a164da8414ef3791fb9717bcc190
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233701"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="33eca-103">Ver la actividad en el contenido de la etiqueta (vista previa)</span><span class="sxs-lookup"><span data-stu-id="33eca-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="33eca-104">La descripción general de la clasificación de datos y las pestañas del explorador de contenido le ofrecen visibilidad sobre el contenido que se ha descubierto y etiquetado, y dónde está ese contenido.</span><span class="sxs-lookup"><span data-stu-id="33eca-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="33eca-105">El explorador de actividad complementa este conjunto de funciones permitiéndole supervisar lo que se lleva a cabo con el contenido de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="33eca-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="33eca-106">El explorador de actividad ofrece una vista histórica.</span><span class="sxs-lookup"><span data-stu-id="33eca-106">Activity explorer provides a historical view.</span></span>

![Marcador de posición captura de pantalla información general explorador de actividad](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="33eca-108">Puede filtrar los datos de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="33eca-108">You can filter the data by:</span></span>

- <span data-ttu-id="33eca-109">Intervalo de fechas:</span><span class="sxs-lookup"><span data-stu-id="33eca-109">date range</span></span>
- <span data-ttu-id="33eca-110">TIPO DE ACTIVIDAD</span><span class="sxs-lookup"><span data-stu-id="33eca-110">activity type</span></span>
- <span data-ttu-id="33eca-111">Ubicación</span><span class="sxs-lookup"><span data-stu-id="33eca-111">location</span></span>
- <span data-ttu-id="33eca-112">Usuario</span><span class="sxs-lookup"><span data-stu-id="33eca-112">user</span></span>
- <span data-ttu-id="33eca-113">Etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="33eca-113">sensitivity label</span></span>
- <span data-ttu-id="33eca-114">Etiqueta de retención:</span><span class="sxs-lookup"><span data-stu-id="33eca-114">retention label</span></span>


<span data-ttu-id="33eca-115">Puede ver los datos como una lista o un gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="33eca-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="33eca-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="33eca-116">Prerequisites</span></span>

<span data-ttu-id="33eca-117">Todas las cuentas que tienen acceso al explorador de actividad y lo usan deben tener una licencia de asignada de una de estas suscripciones:</span><span class="sxs-lookup"><span data-stu-id="33eca-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="33eca-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="33eca-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="33eca-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="33eca-119">Office 365 E5</span></span>
- <span data-ttu-id="33eca-120">Complemento de cumplimiento avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="33eca-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="33eca-121">Complemento de inteligencia de amenazas avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="33eca-121">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="33eca-122">Complemento de protección contra amenazas avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="33eca-122">Advanced Threat Protection (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="33eca-123">Tipo de actividad</span><span class="sxs-lookup"><span data-stu-id="33eca-123">Activity type</span></span>

<span data-ttu-id="33eca-124">Microsoft 365 supervisa y realiza un seguimiento de los 12 tipos de actividades en SharePoint Online, OneDrive y los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="33eca-124">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="33eca-125">Los puntos de conexión son dispositivos de usuario que ejecutan Windows 10.</span><span class="sxs-lookup"><span data-stu-id="33eca-125">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="33eca-126">Archivo creado</span><span class="sxs-lookup"><span data-stu-id="33eca-126">File created</span></span>
- <span data-ttu-id="33eca-127">Archivo modificado</span><span class="sxs-lookup"><span data-stu-id="33eca-127">File modified</span></span>
- <span data-ttu-id="33eca-128">Archivo con el nombre cambiado</span><span class="sxs-lookup"><span data-stu-id="33eca-128">File renamed</span></span>
- <span data-ttu-id="33eca-129">Archivo copiado en la nube</span><span class="sxs-lookup"><span data-stu-id="33eca-129">File copied to cloud</span></span>
- <span data-ttu-id="33eca-130">Archivo al que se ha accedido mediante una aplicación no permitida</span><span class="sxs-lookup"><span data-stu-id="33eca-130">File accessed by unallowed app</span></span>
- <span data-ttu-id="33eca-131">Archivo impreso</span><span class="sxs-lookup"><span data-stu-id="33eca-131">File printed</span></span>
- <span data-ttu-id="33eca-132">Archivo copiado en un medio extraíble</span><span class="sxs-lookup"><span data-stu-id="33eca-132">File copied to removable media</span></span>
- <span data-ttu-id="33eca-133">Archivo copiado al recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="33eca-133">File copied to network share</span></span>
- <span data-ttu-id="33eca-134">Archivo leído</span><span class="sxs-lookup"><span data-stu-id="33eca-134">File read</span></span>
- <span data-ttu-id="33eca-135">archivo copiado en el portapapeles</span><span class="sxs-lookup"><span data-stu-id="33eca-135">file copied to clipboard</span></span>
- <span data-ttu-id="33eca-136">Etiqueta aplicada</span><span class="sxs-lookup"><span data-stu-id="33eca-136">Label applied</span></span>
- <span data-ttu-id="33eca-137">Etiqueta cambiada (actualizada, degradada o eliminada)</span><span class="sxs-lookup"><span data-stu-id="33eca-137">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="33eca-138">El valor de comprensión de las acciones que se toman con el contenido identificado por la etiqueta es que puede ver si los controles que ya se han puesto en su sitio, como [Directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) son efectivas o no.</span><span class="sxs-lookup"><span data-stu-id="33eca-138">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="33eca-139">Si no es así, o si se detecta algo inesperado, como un gran número de elementos etiquetados `highly confidential`y se degradan`general`, puede administrar las distintas directivas y llevar a cabo nuevas acciones para restringir el comportamiento no deseado.</span><span class="sxs-lookup"><span data-stu-id="33eca-139">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="33eca-140">Una vez que haya establecido los filtros, puede:</span><span class="sxs-lookup"><span data-stu-id="33eca-140">Once your filters are set, you can:</span></span>

- <span data-ttu-id="33eca-141">Mantenga el mouse sobre un segmento del gráfico de barras para ver el número de elementos que se encuentran en la categoría ![el explorador de actividad desplace el puntero sobre](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="33eca-141">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="33eca-142">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="33eca-142">export the data</span></span>
- <span data-ttu-id="33eca-143">seleccionar un elemento determinado de la lista y ver los detalles de la acción en el menú desplegable</span><span class="sxs-lookup"><span data-stu-id="33eca-143">select any given item from the list and view the details of the action in the fly-out</span></span>

![menú desplegable con los detalles del explorador de actividad](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="33eca-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="33eca-145">See also</span></span>
- [<span data-ttu-id="33eca-146">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="33eca-146">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="33eca-147">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="33eca-147">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="33eca-148">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="33eca-148">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="33eca-149">Información general sobre las directivas de retención</span><span class="sxs-lookup"><span data-stu-id="33eca-149">Overview of retention policies</span></span>](retention-policies.md)