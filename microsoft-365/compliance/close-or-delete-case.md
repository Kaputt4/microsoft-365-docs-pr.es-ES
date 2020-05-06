---
title: Cerrar o eliminar un caso
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
description: Obtenga información acerca de lo que sucede cuando una investigación o un caso legal admitido por un caso de exhibición de documentos electrónicos se cierra o se elimina.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f91755e6d2aeba89e795a623cd1268af0a53e675
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035642"
---
# <a name="close-or-delete-a-case"></a><span data-ttu-id="1ba80-103">Cerrar o eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="1ba80-103">Close or delete a case</span></span>

<span data-ttu-id="1ba80-104">Cuando se completa el caso legal o la investigación admitidos por un caso de exhibición de documentos electrónicos, puede cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="1ba80-104">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="1ba80-105">Esto es lo que sucede cuando se cierra un caso:</span><span class="sxs-lookup"><span data-stu-id="1ba80-105">Here's what happens when you close a case:</span></span>

- <span data-ttu-id="1ba80-106">Si el caso contiene ubicaciones de contenido en suspensión, dichas suspensiones se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="1ba80-106">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="1ba80-107">Esto puede dar lugar a que el usuario o un proceso automatizado eliminen o purguen permanentemente el contenido, como una directiva de eliminación.</span><span class="sxs-lookup"><span data-stu-id="1ba80-107">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="1ba80-108">Si se cierra un caso, sólo se desactivan las suspensiones asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="1ba80-108">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="1ba80-109">Si otras suspensiones se colocan en una ubicación de contenido (como una retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="1ba80-109">If other holds are place on a content location (such as a Litigation Hold.</span></span> <span data-ttu-id="1ba80-110">una directiva de conservación o una retención de un caso de exhibición de documentos electrónicos diferente, se conservarán las suspensiones.</span><span class="sxs-lookup"><span data-stu-id="1ba80-110">a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="1ba80-111">El caso todavía aparece en la página exhibición de documentos electrónicos del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1ba80-111">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="1ba80-112">Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="1ba80-112">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="1ba80-113">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="1ba80-113">You can edit a case after it's closed.</span></span> <span data-ttu-id="1ba80-114">Por ejemplo, puede Agregar o quitar miembros, crear búsquedas, exportar los resultados de la búsqueda y preparar los resultados de la búsqueda para analizarlos en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="1ba80-114">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="1ba80-115">La principal diferencia entre los casos activos y cerrados es que las suspensiones se desactivan cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="1ba80-115">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="1ba80-116">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="1ba80-116">To close a case:</span></span>

1. <span data-ttu-id="1ba80-117">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera cerrar.</span><span class="sxs-lookup"><span data-stu-id="1ba80-117">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="1ba80-118">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1ba80-118">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="1ba80-119">Haga clic en **cerrar caso**.</span><span class="sxs-lookup"><span data-stu-id="1ba80-119">Click **Close case**.</span></span>

<span data-ttu-id="1ba80-120">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="1ba80-120">To delete a case:</span></span>

1. <span data-ttu-id="1ba80-121">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="1ba80-121">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="1ba80-122">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1ba80-122">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="1ba80-123">Haga clic en **eliminar caso**.</span><span class="sxs-lookup"><span data-stu-id="1ba80-123">Click **Delete case**.</span></span> 
