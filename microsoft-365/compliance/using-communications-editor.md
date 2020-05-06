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
ms.openlocfilehash: 0cb415da9aa09452176bd8aa9be4575cfc827582
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034482"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="06a04-103">Usar el editor de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="06a04-103">Use the communications editor</span></span>

<span data-ttu-id="06a04-104">Al definir el contenido del contenido del portal, las notificaciones de retención legal y los avisos/escalas relacionados, puede aprovechar el editor de comunicaciones para formatear y personalizar el contenido de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="06a04-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="06a04-105">Editor de texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="06a04-105">Rich text editor</span></span> 

<span data-ttu-id="06a04-106">El editor de comunicaciones permite al usuario personalizar el texto con las opciones del editor.</span><span class="sxs-lookup"><span data-stu-id="06a04-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="06a04-107">Por ejemplo, los usuarios pueden cambiar los tipos de fuente, crear listas con viñetas, resaltar contenido, etc.</span><span class="sxs-lookup"><span data-stu-id="06a04-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="06a04-108">Combinar variables de campo</span><span class="sxs-lookup"><span data-stu-id="06a04-108">Merge field variables</span></span>

<span data-ttu-id="06a04-109">Puede aprovechar las variables de combinación de correo electrónico del editor de comunicaciones para incrustar atributos de custodios personalizados en el texto del cuerpo de una comunicación.</span><span class="sxs-lookup"><span data-stu-id="06a04-109">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="06a04-110">Cuando se envía al custodio, el campo de combinación se rellenará con el campo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="06a04-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="06a04-111">Por ejemplo, cuando se envía a custodio Andrés Díaz, el campo de combinación [nombre del custodio] se convertiría con el nombre correspondiente.</span><span class="sxs-lookup"><span data-stu-id="06a04-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="06a04-112">Puede usar los campos de combinación de correo electrónico seleccionando los iconos de **campo de combinación** en la parte superior del control del editor de texto enriquecido.</span><span class="sxs-lookup"><span data-stu-id="06a04-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="06a04-113">El marcador de posición se agregará en función de la ubicación del cursor de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="06a04-113">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="06a04-114">Lista de variables de campo de combinación</span><span class="sxs-lookup"><span data-stu-id="06a04-114">List of merge field variables</span></span>

| <span data-ttu-id="06a04-115">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="06a04-115">Field name</span></span>                  | <span data-ttu-id="06a04-116">Detalles de campo</span><span class="sxs-lookup"><span data-stu-id="06a04-116">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="06a04-117">Nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="06a04-117">Display Name</span></span>  | <span data-ttu-id="06a04-118">Nombre y apellido del custodio.</span><span class="sxs-lookup"><span data-stu-id="06a04-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="06a04-119">Vínculo de confirmación</span><span class="sxs-lookup"><span data-stu-id="06a04-119">Acknowledgement Link</span></span> | <span data-ttu-id="06a04-120">Un vínculo personalizado para registrar la confirmación de cada custodio.</span><span class="sxs-lookup"><span data-stu-id="06a04-120">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="06a04-121">Vínculo al portal</span><span class="sxs-lookup"><span data-stu-id="06a04-121">Portal Link</span></span>     | <span data-ttu-id="06a04-122">Un vínculo personalizado para el portal de cumplimiento de la custodio.</span><span class="sxs-lookup"><span data-stu-id="06a04-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="06a04-123">Responsable de la expedición</span><span class="sxs-lookup"><span data-stu-id="06a04-123">Issuing Officer</span></span>                   | <span data-ttu-id="06a04-124">La dirección de correo electrónico del oficial de expedición especificado.</span><span class="sxs-lookup"><span data-stu-id="06a04-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="06a04-125">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="06a04-125">Issuing Date</span></span>                   | <span data-ttu-id="06a04-126">La fecha en que se emitió el aviso (UTC).</span><span class="sxs-lookup"><span data-stu-id="06a04-126">The date that the notice was issued (UTC).</span></span>              |
