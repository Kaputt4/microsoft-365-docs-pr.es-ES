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
description: Use el Editor de comunicaciones para cambiar el texto y combinar variables de campo al dar formato al contenido.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 26076ff82ba226c2993c7c40e36bca2e08cbf683
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288124"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="6169b-103">Usar el editor de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="6169b-103">Use the communications editor</span></span>

<span data-ttu-id="6169b-104">A medida que defina el contenido del portal, las notificaciones de retención legal y los avisos o escalaciones relacionados, puede usar el Editor de comunicaciones para dar formato y personalizar dinámicamente el contenido.</span><span class="sxs-lookup"><span data-stu-id="6169b-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="6169b-105">Editor de texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="6169b-105">Rich text editor</span></span>

<span data-ttu-id="6169b-106">El Editor de comunicaciones permite al usuario personalizar el texto con las opciones del editor.</span><span class="sxs-lookup"><span data-stu-id="6169b-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="6169b-107">Por ejemplo, los usuarios pueden cambiar tipos de fuentes, crear listas con viñetas, resaltar contenido y mucho más.</span><span class="sxs-lookup"><span data-stu-id="6169b-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="6169b-108">Combinar variables de campo</span><span class="sxs-lookup"><span data-stu-id="6169b-108">Merge field variables</span></span>

<span data-ttu-id="6169b-109">Puede usar variables de combinación de correo electrónico desde el Editor de comunicaciones para insertar atributos de custodia personalizados en el texto del cuerpo de una comunicación.</span><span class="sxs-lookup"><span data-stu-id="6169b-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="6169b-110">Cuando se envía al custodio, el campo de combinación se rellenará con el campo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6169b-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="6169b-111">Por ejemplo, cuando se envía al custodio John Smith, el campo de combinación [Nombre del custodio] se traduciría con el nombre correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6169b-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="6169b-112">Puede usar los campos de combinación de correo electrónico seleccionando los **iconos** del campo Combinar en la parte superior del control del editor de texto enriquecido.</span><span class="sxs-lookup"><span data-stu-id="6169b-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="6169b-113">El marcador de posición se agregará en función de la ubicación del cursor de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6169b-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="6169b-114">Lista de variables de campo de combinación</span><span class="sxs-lookup"><span data-stu-id="6169b-114">List of merge field variables</span></span>

<br>

****

|<span data-ttu-id="6169b-115">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="6169b-115">Field name</span></span>|<span data-ttu-id="6169b-116">Detalles del campo</span><span class="sxs-lookup"><span data-stu-id="6169b-116">Field details</span></span>|
|---|---|
|<span data-ttu-id="6169b-117">Nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="6169b-117">Display Name</span></span>|<span data-ttu-id="6169b-118">Nombre y apellidos del custodio.</span><span class="sxs-lookup"><span data-stu-id="6169b-118">The custodian's first and last name.</span></span>|
|<span data-ttu-id="6169b-119">Vínculo de confirmación</span><span class="sxs-lookup"><span data-stu-id="6169b-119">Acknowledgment Link</span></span>|<span data-ttu-id="6169b-120">Un vínculo personalizado para registrar el acuse de recibo de cada custodio.</span><span class="sxs-lookup"><span data-stu-id="6169b-120">A customized link to record each custodian's acknowledgment.</span></span>|
|<span data-ttu-id="6169b-121">Vínculo portal</span><span class="sxs-lookup"><span data-stu-id="6169b-121">Portal Link</span></span>|<span data-ttu-id="6169b-122">Vínculo personalizado para el Portal de cumplimiento del custodio.</span><span class="sxs-lookup"><span data-stu-id="6169b-122">A customized link for the custodian's Compliance Portal.</span></span>|
|<span data-ttu-id="6169b-123">Oficial emisor</span><span class="sxs-lookup"><span data-stu-id="6169b-123">Issuing Officer</span></span>|<span data-ttu-id="6169b-124">La dirección de correo electrónico del oficial emisor especificado.</span><span class="sxs-lookup"><span data-stu-id="6169b-124">The email address of the specified issuing officer.</span></span>|
|<span data-ttu-id="6169b-125">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="6169b-125">Issuing Date</span></span>|<span data-ttu-id="6169b-126">La fecha en que se emitió el aviso (UTC).</span><span class="sxs-lookup"><span data-stu-id="6169b-126">The date that the notice was issued (UTC).</span></span>|
|
