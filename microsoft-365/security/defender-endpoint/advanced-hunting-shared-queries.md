---
title: Utilice las consultas compartidas en la búsqueda avanzada
description: Inicie inmediatamente la protección contra amenazas a través de las consultas predefinidas y compartidas. Comparta sus consultas con el público o con su organización.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, telemetría, detecciones personalizadas, esquema, kusto, repositorio de github, mis consultas, consultas compartidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075467"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="c2ccb-105">Utilice las consultas compartidas en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c2ccb-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c2ccb-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c2ccb-106">**Applies to:**</span></span>
- [<span data-ttu-id="c2ccb-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c2ccb-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="c2ccb-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c2ccb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c2ccb-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="c2ccb-110">Las consultas en la [búsqueda avanzada](advanced-hunting-overview.md) pueden ser compartidas entre usuarios de la misma organización.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="c2ccb-111">También puede buscar las consultas compartidas de forma pública en GitHub.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="c2ccb-112">Estas consultas le permitirán seguir rápidamente los escenarios específicos de búsqueda contra amenazas sin tener que escribir las consultas desde cero.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagen de las consultas compartidas](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="c2ccb-114">Guardar, modificar y compartir la consulta</span><span class="sxs-lookup"><span data-stu-id="c2ccb-114">Save, modify, and share a query</span></span>
<span data-ttu-id="c2ccb-115">Puede guardar una consulta nueva o existente para que sólo sea accesible para usted o compartida con otros usuarios en su organización.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="c2ccb-116">Escriba una nueva consulta o cargue una existente desde **en Consultas compartidas** o **Mis consultas**.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="c2ccb-117">Seleccione **Guardar** o **Guardar como en** las opciones de guardar.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="c2ccb-118">Para evitar sobrescribir una consulta existente, elija **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="c2ccb-119">Escriba un nombre para la consulta.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-119">Enter a name for the query.</span></span>

   ![Imagen de una consulta guardada](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="c2ccb-121">Seleccione la carpeta en la que desea guardar la consulta.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="c2ccb-122">**Consultas compartidas:** compartidas para todos los usuarios de la organización</span><span class="sxs-lookup"><span data-stu-id="c2ccb-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="c2ccb-123">**Mis consultas** — accesibles sólo para usted.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="c2ccb-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="c2ccb-125">Eliminar o cambiar el nombre de la consulta</span><span class="sxs-lookup"><span data-stu-id="c2ccb-125">Delete or rename a query</span></span>
1. <span data-ttu-id="c2ccb-126">Haga clic con el botón derecho en la consulta que desee cambiar o eliminar el nombre.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-126">Right-click on a query you want to rename or delete.</span></span>

    ![Imagen de una consulta eliminada](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="c2ccb-128">Seleccione **Eliminar** y confirme su eliminación.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="c2ccb-129">O seleccione **Cambiar el nombre** y proporcione un nombre nuevo para la consulta.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="c2ccb-130">Crear un vínculo directo a una consulta</span><span class="sxs-lookup"><span data-stu-id="c2ccb-130">Create a direct link to a query</span></span>
<span data-ttu-id="c2ccb-131">Para generar un vínculo que abra la consulta directamente en el editor de consultas de búsqueda avanzada, finalizar la consulta y seleccionar **Compartir vínculo**.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="c2ccb-132">Acceder a las consultas en el repositorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="c2ccb-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="c2ccb-133">Los investigadores de la seguridad de Microsoft comparten regularmente las consultas de búsquedas avanzadas en un [repositorio público designado en GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span><span class="sxs-lookup"><span data-stu-id="c2ccb-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="c2ccb-134">Este repositorio está abierto a contribuciones.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-134">This repository is open to contributions.</span></span> <span data-ttu-id="c2ccb-135">Para contribuir, [únete a GitHub gratis](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="c2ccb-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="c2ccb-136">Los investigadores de la seguridad de Microsoft también proporcionan búsquedas avanzadas que puede ser utilizadas para buscar actividades e indicadores asociados a las amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="c2ccb-137">Estas consultas son proporcionadas en los informes del [análisis de amenazas](threat-analytics.md) del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c2ccb-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c2ccb-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c2ccb-138">Related topics</span></span>
- [<span data-ttu-id="c2ccb-139">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c2ccb-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c2ccb-140">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="c2ccb-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c2ccb-141">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="c2ccb-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="c2ccb-142">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="c2ccb-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="c2ccb-143">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="c2ccb-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c2ccb-144">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="c2ccb-144">Custom detections overview</span></span>](overview-custom-detections.md)
