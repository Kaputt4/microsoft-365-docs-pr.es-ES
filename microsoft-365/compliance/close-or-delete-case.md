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
description: " "
ms.openlocfilehash: 15b6327809b3557c4d0d90b6c10dc5568ba47f43
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595877"
---
# <a name="close-or-delete-a-case"></a><span data-ttu-id="44beb-102">Cerrar o eliminar un caso</span><span class="sxs-lookup"><span data-stu-id="44beb-102">Close or delete a case</span></span>

<span data-ttu-id="44beb-103">Cuando se completa el caso legal o la investigación admitidos por un caso de exhibición de documentos electrónicos, puede cerrar el caso.</span><span class="sxs-lookup"><span data-stu-id="44beb-103">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="44beb-104">Esto es lo que sucede cuando se cierra un caso:</span><span class="sxs-lookup"><span data-stu-id="44beb-104">Here's what happens when you close a case:</span></span>

- <span data-ttu-id="44beb-105">Si el caso contiene ubicaciones de contenido en suspensión, dichas suspensiones se desactivarán.</span><span class="sxs-lookup"><span data-stu-id="44beb-105">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="44beb-106">Esto puede dar lugar a que el usuario o un proceso automatizado eliminen o purguen permanentemente el contenido, como una directiva de eliminación.</span><span class="sxs-lookup"><span data-stu-id="44beb-106">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="44beb-107">Si se cierra un caso, sólo se desactivan las suspensiones asociadas a ese caso.</span><span class="sxs-lookup"><span data-stu-id="44beb-107">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="44beb-108">Si otras suspensiones se colocan en una ubicación de contenido (como una retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="44beb-108">If other holds are place on a content location (such as a Litigation Hold.</span></span> <span data-ttu-id="44beb-109">una directiva de conservación o una retención de un caso de exhibición de documentos electrónicos diferente, se conservarán las suspensiones.</span><span class="sxs-lookup"><span data-stu-id="44beb-109">a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="44beb-110">El caso todavía aparece en la página exhibición de documentos electrónicos del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="44beb-110">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="44beb-111">Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.</span><span class="sxs-lookup"><span data-stu-id="44beb-111">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="44beb-112">Puede editar un caso después de cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="44beb-112">You can edit a case after it's closed.</span></span> <span data-ttu-id="44beb-113">Por ejemplo, puede Agregar o quitar miembros, crear búsquedas, exportar los resultados de la búsqueda y preparar los resultados de la búsqueda para analizarlos en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="44beb-113">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="44beb-114">La principal diferencia entre los casos activos y cerrados es que las suspensiones se desactivan cuando se cierra un caso.</span><span class="sxs-lookup"><span data-stu-id="44beb-114">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="44beb-115">Para cerrar un caso:</span><span class="sxs-lookup"><span data-stu-id="44beb-115">To close a case:</span></span>

1. <span data-ttu-id="44beb-116">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera cerrar.</span><span class="sxs-lookup"><span data-stu-id="44beb-116">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="44beb-117">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="44beb-117">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="44beb-118">Haga clic en **cerrar caso**.</span><span class="sxs-lookup"><span data-stu-id="44beb-118">Click **Close case**.</span></span>

<span data-ttu-id="44beb-119">Para eliminar un caso:</span><span class="sxs-lookup"><span data-stu-id="44beb-119">To delete a case:</span></span>

1. <span data-ttu-id="44beb-120">En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="44beb-120">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="44beb-121">En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="44beb-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="44beb-122">Haga clic en **eliminar caso**.</span><span class="sxs-lookup"><span data-stu-id="44beb-122">Click **Delete case**.</span></span> 
