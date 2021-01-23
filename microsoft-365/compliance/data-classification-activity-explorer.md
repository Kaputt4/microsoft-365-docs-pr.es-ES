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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El explorador de actividad complementa la funcionalidad de la característica de clasificación de datos permitiéndole ver y filtrar las acciones que los usuarios están realizando en el contenido etiquetado.
ms.openlocfilehash: 6825c00373617011db28fa484f272086f887ea40
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921638"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="a4d52-103">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="a4d52-103">Get started with activity explorer</span></span>

<span data-ttu-id="a4d52-104">La descripción general de la clasificación de datos y las pestañas del explorador de contenido le ofrecen visibilidad sobre el contenido que se ha descubierto y etiquetado, y dónde está ese contenido.</span><span class="sxs-lookup"><span data-stu-id="a4d52-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="a4d52-105">El explorador de actividad complementa este conjunto de funciones permitiéndole supervisar lo que se lleva a cabo con el contenido de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a4d52-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="a4d52-106">El explorador de actividad ofrece una vista histórica.</span><span class="sxs-lookup"><span data-stu-id="a4d52-106">Activity explorer provides a historical view.</span></span>

![Marcador de posición captura de pantalla información general explorador de actividad](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="a4d52-108">Hay más de 30 filtros diferentes disponibles, estos son algunos:</span><span class="sxs-lookup"><span data-stu-id="a4d52-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="a4d52-109">Intervalo de fechas:</span><span class="sxs-lookup"><span data-stu-id="a4d52-109">date range</span></span>
- <span data-ttu-id="a4d52-110">TIPO DE ACTIVIDAD</span><span class="sxs-lookup"><span data-stu-id="a4d52-110">activity type</span></span>
- <span data-ttu-id="a4d52-111">Ubicación</span><span class="sxs-lookup"><span data-stu-id="a4d52-111">location</span></span>
- <span data-ttu-id="a4d52-112">Usuario</span><span class="sxs-lookup"><span data-stu-id="a4d52-112">user</span></span>
- <span data-ttu-id="a4d52-113">Etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="a4d52-113">sensitivity label</span></span>
- <span data-ttu-id="a4d52-114">Etiqueta de retención:</span><span class="sxs-lookup"><span data-stu-id="a4d52-114">retention label</span></span>
- <span data-ttu-id="a4d52-115">ruta de acceso del archivo</span><span class="sxs-lookup"><span data-stu-id="a4d52-115">file path</span></span>
- <span data-ttu-id="a4d52-116">Directiva DLP</span><span class="sxs-lookup"><span data-stu-id="a4d52-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="a4d52-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a4d52-117">Prerequisites</span></span>

<span data-ttu-id="a4d52-118">Todas las cuentas que tienen acceso a la clasificación de datos y la usan deben tener una licencia asignada de una de estas suscripciones:</span><span class="sxs-lookup"><span data-stu-id="a4d52-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="a4d52-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a4d52-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="a4d52-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a4d52-120">Office 365 (E5)</span></span>
- <span data-ttu-id="a4d52-121">Complemento de cumplimiento avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="a4d52-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="a4d52-122">Complemento de inteligencia de amenazas avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="a4d52-122">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="a4d52-123">Gobernanza y protección de la información de Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="a4d52-123">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="a4d52-124">Cumplimiento de Microsoft 365 E5/A5 </span><span class="sxs-lookup"><span data-stu-id="a4d52-124">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="a4d52-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="a4d52-125">Permissions</span></span>

 <span data-ttu-id="a4d52-126">Para obtener acceso a la pestaña del explorador de actividad, una cuenta debe tener asignada una suscripción en cualquiera de estos roles o grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="a4d52-126">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="a4d52-127">**Grupos de roles de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="a4d52-127">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="a4d52-128">Administrador global</span><span class="sxs-lookup"><span data-stu-id="a4d52-128">Global administrator</span></span>
- <span data-ttu-id="a4d52-129">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a4d52-129">Compliance administrator</span></span>
- <span data-ttu-id="a4d52-130">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="a4d52-130">Security administrator</span></span>
- <span data-ttu-id="a4d52-131">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a4d52-131">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="a4d52-132">Tipo de actividad</span><span class="sxs-lookup"><span data-stu-id="a4d52-132">Activity type</span></span>

<span data-ttu-id="a4d52-133">Microsoft 365 supervisa y realiza un seguimiento de los tipos de actividades en SharePoint Online y OneDrive, como:</span><span class="sxs-lookup"><span data-stu-id="a4d52-133">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="a4d52-134">etiqueta aplicada</span><span class="sxs-lookup"><span data-stu-id="a4d52-134">label applied</span></span>
- <span data-ttu-id="a4d52-135">etiqueta cambiada (actualizada, degradada o eliminada)</span><span class="sxs-lookup"><span data-stu-id="a4d52-135">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="a4d52-136">simulación de etiquetado automático</span><span class="sxs-lookup"><span data-stu-id="a4d52-136">auto-labeling simulation</span></span>

<span data-ttu-id="a4d52-137">El valor de comprensión de las acciones que se toman con el contenido identificado por la etiqueta es que puede ver si los controles que ya se han puesto en su sitio, como [Directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) son efectivas o no.</span><span class="sxs-lookup"><span data-stu-id="a4d52-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="a4d52-138">Si no es así, o si se detecta algo inesperado, como un gran número de elementos etiquetados `highly confidential`y se degradan`general`, puede administrar las distintas directivas y llevar a cabo nuevas acciones para restringir el comportamiento no deseado.</span><span class="sxs-lookup"><span data-stu-id="a4d52-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="a4d52-139">El explorador de actividad no supervisa actualmente las actividades de retención de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a4d52-139">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4d52-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a4d52-140">See also</span></span>
- [<span data-ttu-id="a4d52-141">Información sobre las etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="a4d52-141">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a4d52-142">Más información sobre las directivas y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="a4d52-142">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="a4d52-143">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="a4d52-143">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

