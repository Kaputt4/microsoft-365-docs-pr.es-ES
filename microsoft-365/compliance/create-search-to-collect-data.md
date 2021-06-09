---
title: Crear una búsqueda
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
description: Obtenga información sobre cómo crear, definir y elegir custodios y ubicaciones de custodia para una búsqueda en un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035772"
---
# <a name="create-a-search"></a><span data-ttu-id="b1c13-103">Crear una búsqueda</span><span class="sxs-lookup"><span data-stu-id="b1c13-103">Create a search</span></span>

<span data-ttu-id="b1c13-104">En la **pestaña** Búsquedas del caso, puede crear una nueva búsqueda haciendo clic en **Nueva búsqueda** y siguiendo el asistente.</span><span class="sxs-lookup"><span data-stu-id="b1c13-104">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![El asistente de búsqueda en un Advanced eDiscovery caso](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="b1c13-106">Asigne un nombre a la búsqueda y déle una descripción.</span><span class="sxs-lookup"><span data-stu-id="b1c13-106">Name the search and give it a description</span></span>

<span data-ttu-id="b1c13-107">Cada búsqueda con un caso debe tener un nombre único.</span><span class="sxs-lookup"><span data-stu-id="b1c13-107">Each search with a case should have a unique name.</span></span> <span data-ttu-id="b1c13-108">Opcionalmente, puede proporcionar una descripción para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b1c13-108">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="b1c13-109">Elegir los custodios y ubicaciones de custodia para buscar</span><span class="sxs-lookup"><span data-stu-id="b1c13-109">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="b1c13-110">Elija ubicaciones de contenido de custodia para buscar especificando los custodios que ha agregado al caso.</span><span class="sxs-lookup"><span data-stu-id="b1c13-110">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="b1c13-111">Al seleccionar un custodio, ejecutará la búsqueda en todos los orígenes de datos asignados al custodio.</span><span class="sxs-lookup"><span data-stu-id="b1c13-111">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="b1c13-112">También tiene la opción de restringir la búsqueda a orígenes de datos seleccionados para cada custodio.</span><span class="sxs-lookup"><span data-stu-id="b1c13-112">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="b1c13-113">Para obtener más información acerca de cómo agregar custodios y administrar sus orígenes de datos, vea [Trabajar con custodios.](managing-custodians.md)</span><span class="sxs-lookup"><span data-stu-id="b1c13-113">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="b1c13-114">Elegir ubicaciones sin custodia</span><span class="sxs-lookup"><span data-stu-id="b1c13-114">Choose non-custodial locations</span></span>

<span data-ttu-id="b1c13-115">En algunos casos, es posible que desee buscar orígenes de datos que no estén asociados con un custodio.</span><span class="sxs-lookup"><span data-stu-id="b1c13-115">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="b1c13-116">En este caso, puede especificar las ubicaciones que desea buscar o elegir buscar en todas las ubicaciones de contenido para un servicio de Microsoft específico (como buscar todos los buzones de Exchange o todos los sitios SharePoint y OneDrive cuentas).</span><span class="sxs-lookup"><span data-stu-id="b1c13-116">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="b1c13-117">Definir las condiciones y la consulta de búsqueda</span><span class="sxs-lookup"><span data-stu-id="b1c13-117">Define the search query and conditions</span></span>

<span data-ttu-id="b1c13-118">Puede definir la consulta de palabras clave y cualquier condición para la búsqueda mediante las tarjetas de condición predefinidas o mediante lenguaje de consulta de palabras clave (KQL).</span><span class="sxs-lookup"><span data-stu-id="b1c13-118">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="b1c13-119">Para obtener más información, vea [Generar consultas de búsqueda](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="b1c13-119">For more information, see [Build search queries](building-search-queries.md).</span></span>
