---
title: Usar el explorador de actividad de clasificación de datos
f1.keywords:
- NOCSH
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
ms.openlocfilehash: f80ce94433028b2434d442a364c336060b730d94
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076784"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="b00e3-103">Ver la actividad en el contenido de la etiqueta (vista previa)</span><span class="sxs-lookup"><span data-stu-id="b00e3-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="b00e3-104">La descripción general de la clasificación de datos y las pestañas del explorador de contenido le ofrecen visibilidad sobre el contenido que se ha descubierto y etiquetado, y dónde está ese contenido.</span><span class="sxs-lookup"><span data-stu-id="b00e3-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="b00e3-105">El explorador de actividad complementa este conjunto de funciones permitiéndole supervisar lo que se lleva a cabo con el contenido de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="b00e3-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="b00e3-106">El explorador de actividad ofrece una vista histórica.</span><span class="sxs-lookup"><span data-stu-id="b00e3-106">Activity explorer provides a historical view.</span></span>

![Marcador de posición captura de pantalla información general explorador de actividad](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="b00e3-108">Puede filtrar los datos de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b00e3-108">You can filter the data by:</span></span>

- <span data-ttu-id="b00e3-109">Intervalo de fechas:</span><span class="sxs-lookup"><span data-stu-id="b00e3-109">date range</span></span>
- <span data-ttu-id="b00e3-110">TIPO DE ACTIVIDAD</span><span class="sxs-lookup"><span data-stu-id="b00e3-110">activity type</span></span>
- <span data-ttu-id="b00e3-111">Ubicación</span><span class="sxs-lookup"><span data-stu-id="b00e3-111">location</span></span>
- <span data-ttu-id="b00e3-112">Usuario</span><span class="sxs-lookup"><span data-stu-id="b00e3-112">user</span></span>
- <span data-ttu-id="b00e3-113">Etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="b00e3-113">sensitivity label</span></span>
- <span data-ttu-id="b00e3-114">Etiqueta de retención:</span><span class="sxs-lookup"><span data-stu-id="b00e3-114">retention label</span></span>


<span data-ttu-id="b00e3-115">Puede ver los datos como una lista o un gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="b00e3-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b00e3-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b00e3-116">Prerequisites</span></span>

<span data-ttu-id="b00e3-117">Todas las cuentas que tienen acceso al explorador de actividad y lo usan deben tener una licencia de asignada de una de estas suscripciones:</span><span class="sxs-lookup"><span data-stu-id="b00e3-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="b00e3-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="b00e3-118">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="b00e3-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="b00e3-119">Office 365 (E5)</span></span>
- <span data-ttu-id="b00e3-120">Complemento de cumplimiento avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="b00e3-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="b00e3-121">Complemento de inteligencia de amenazas avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="b00e3-121">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="b00e3-122">Tipo de actividad</span><span class="sxs-lookup"><span data-stu-id="b00e3-122">Activity type</span></span>

<span data-ttu-id="b00e3-123">Microsoft 365 supervisa y realiza un seguimiento de los 12 tipos de actividades en SharePoint Online, OneDrive y los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="b00e3-123">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="b00e3-124">Los puntos de conexión son dispositivos de usuario que ejecutan Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b00e3-124">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="b00e3-125">Archivo creado</span><span class="sxs-lookup"><span data-stu-id="b00e3-125">File created</span></span>
- <span data-ttu-id="b00e3-126">Archivo modificado</span><span class="sxs-lookup"><span data-stu-id="b00e3-126">File modified</span></span>
- <span data-ttu-id="b00e3-127">Archivo con el nombre cambiado</span><span class="sxs-lookup"><span data-stu-id="b00e3-127">File renamed</span></span>
- <span data-ttu-id="b00e3-128">Archivo copiado en la nube</span><span class="sxs-lookup"><span data-stu-id="b00e3-128">File copied to cloud</span></span>
- <span data-ttu-id="b00e3-129">Archivo al que se ha accedido mediante una aplicación no permitida</span><span class="sxs-lookup"><span data-stu-id="b00e3-129">File accessed by unallowed app</span></span>
- <span data-ttu-id="b00e3-130">Archivo impreso</span><span class="sxs-lookup"><span data-stu-id="b00e3-130">File printed</span></span>
- <span data-ttu-id="b00e3-131">Archivo copiado en un medio extraíble</span><span class="sxs-lookup"><span data-stu-id="b00e3-131">File copied to removable media</span></span>
- <span data-ttu-id="b00e3-132">Archivo copiado al recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="b00e3-132">File copied to network share</span></span>
- <span data-ttu-id="b00e3-133">Archivo leído</span><span class="sxs-lookup"><span data-stu-id="b00e3-133">File read</span></span>
- <span data-ttu-id="b00e3-134">archivo copiado en el portapapeles</span><span class="sxs-lookup"><span data-stu-id="b00e3-134">file copied to clipboard</span></span>
- <span data-ttu-id="b00e3-135">Etiqueta aplicada</span><span class="sxs-lookup"><span data-stu-id="b00e3-135">Label applied</span></span>
- <span data-ttu-id="b00e3-136">Etiqueta cambiada (actualizada, degradada o eliminada)</span><span class="sxs-lookup"><span data-stu-id="b00e3-136">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="b00e3-137">El valor de comprensión de las acciones que se toman con el contenido identificado por la etiqueta es que puede ver si los controles que ya se han puesto en su sitio, como [Directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) son efectivas o no.</span><span class="sxs-lookup"><span data-stu-id="b00e3-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="b00e3-138">Si no es así, o si se detecta algo inesperado, como un gran número de elementos etiquetados `highly confidential`y se degradan`general`, puede administrar las distintas directivas y llevar a cabo nuevas acciones para restringir el comportamiento no deseado.</span><span class="sxs-lookup"><span data-stu-id="b00e3-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="b00e3-139">Una vez que haya establecido los filtros, puede:</span><span class="sxs-lookup"><span data-stu-id="b00e3-139">Once your filters are set, you can:</span></span>

- <span data-ttu-id="b00e3-140">Mantenga el mouse sobre un segmento del gráfico de barras para ver el número de elementos que se encuentran en la categoría ![el explorador de actividad desplace el puntero sobre](../media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="b00e3-140">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](../media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="b00e3-141">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="b00e3-141">export the data</span></span>
- <span data-ttu-id="b00e3-142">seleccionar un elemento determinado de la lista y ver los detalles de la acción en el menú desplegable</span><span class="sxs-lookup"><span data-stu-id="b00e3-142">select any given item from the list and view the details of the action in the fly-out</span></span>

![menú desplegable con los detalles del explorador de actividad](../media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="b00e3-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="b00e3-144">See also</span></span>
- [<span data-ttu-id="b00e3-145">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="b00e3-145">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="b00e3-146">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="b00e3-146">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="b00e3-147">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="b00e3-147">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="b00e3-148">Información general sobre las directivas de retención</span><span class="sxs-lookup"><span data-stu-id="b00e3-148">Overview of retention policies</span></span>](retention-policies.md)
