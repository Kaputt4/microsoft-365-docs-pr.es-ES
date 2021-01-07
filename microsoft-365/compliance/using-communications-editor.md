---
title: Usar el editor de comunicaciones
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el editor de comunicaciones para cambiar el texto y combinar variables de campo al dar formato al contenido.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769165"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="aeb30-103">Usar el editor de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="aeb30-103">Use the communications editor</span></span>

<span data-ttu-id="aeb30-104">A medida que se define el contenido del contenido del portal, las notificaciones de retención legal y los avisos/escalamientos relacionados, puede usar el editor de comunicaciones para formatear y personalizar el contenido de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="aeb30-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="aeb30-105">Editor de texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="aeb30-105">Rich text editor</span></span>

<span data-ttu-id="aeb30-106">El editor de comunicaciones permite al usuario personalizar el texto con las opciones del editor.</span><span class="sxs-lookup"><span data-stu-id="aeb30-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="aeb30-107">Por ejemplo, los usuarios pueden cambiar los tipos de fuente, crear listas con viñetas, resaltar contenido, etc.</span><span class="sxs-lookup"><span data-stu-id="aeb30-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="aeb30-108">Combinar variables de campo</span><span class="sxs-lookup"><span data-stu-id="aeb30-108">Merge field variables</span></span>

<span data-ttu-id="aeb30-109">Puede usar variables de combinación de correo electrónico del editor de comunicaciones para incrustar atributos de custodios personalizados en el texto del cuerpo de una comunicación.</span><span class="sxs-lookup"><span data-stu-id="aeb30-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="aeb30-110">Cuando se envía al custodio, el campo de combinación se rellenará con el campo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="aeb30-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="aeb30-111">Por ejemplo, cuando se envía a custodio Andrés Díaz, el campo de combinación [nombre del custodio] se convertiría con el nombre correspondiente.</span><span class="sxs-lookup"><span data-stu-id="aeb30-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="aeb30-112">Puede usar los campos de combinación de correo electrónico seleccionando los iconos de **campo de combinación** en la parte superior del control del editor de texto enriquecido.</span><span class="sxs-lookup"><span data-stu-id="aeb30-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="aeb30-113">El marcador de posición se agregará en función de la ubicación del cursor de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="aeb30-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="aeb30-114">Lista de variables de campo de combinación</span><span class="sxs-lookup"><span data-stu-id="aeb30-114">List of merge field variables</span></span>

| <span data-ttu-id="aeb30-115">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="aeb30-115">Field name</span></span>                  | <span data-ttu-id="aeb30-116">Detalles de campo</span><span class="sxs-lookup"><span data-stu-id="aeb30-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="aeb30-117">Nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="aeb30-117">Display Name</span></span>  | <span data-ttu-id="aeb30-118">Nombre y apellido del custodio.</span><span class="sxs-lookup"><span data-stu-id="aeb30-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="aeb30-119">Vínculo de confirmación</span><span class="sxs-lookup"><span data-stu-id="aeb30-119">Acknowledgment Link</span></span> | <span data-ttu-id="aeb30-120">Un vínculo personalizado para registrar la confirmación de cada custodio.</span><span class="sxs-lookup"><span data-stu-id="aeb30-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="aeb30-121">Vínculo al portal</span><span class="sxs-lookup"><span data-stu-id="aeb30-121">Portal Link</span></span>     | <span data-ttu-id="aeb30-122">Un vínculo personalizado para el portal de cumplimiento de la custodio.</span><span class="sxs-lookup"><span data-stu-id="aeb30-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="aeb30-123">Responsable de la expedición</span><span class="sxs-lookup"><span data-stu-id="aeb30-123">Issuing Officer</span></span>                   | <span data-ttu-id="aeb30-124">La dirección de correo electrónico del oficial de expedición especificado.</span><span class="sxs-lookup"><span data-stu-id="aeb30-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="aeb30-125">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="aeb30-125">Issuing Date</span></span>                   | <span data-ttu-id="aeb30-126">La fecha en que se emitió el aviso (UTC).</span><span class="sxs-lookup"><span data-stu-id="aeb30-126">The date that the notice was issued (UTC).</span></span>              |
|||
