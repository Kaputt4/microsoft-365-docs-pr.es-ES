---
title: Utilice las consultas compartidas en la búsqueda avanzada en la Protección contra amenazas de Microsoft
description: Inicie inmediatamente la protección contra amenazas a través de las consultas predefinidas y compartidas. Comparta sus consultas con el público o con su organización.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, repositorio de Github, mis consultas, consultas compartidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3682044ab100d396719e3b7ffe5a6331852d0d55
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201224"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="246e7-105">Utilice las consultas compartidas en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="246e7-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="246e7-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="246e7-106">**Applies to:**</span></span>
- <span data-ttu-id="246e7-107">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="246e7-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="246e7-108">Las consultas en la [búsqueda avanzada](advanced-hunting-overview.md) pueden ser compartidas entre usuarios de la misma organización.</span><span class="sxs-lookup"><span data-stu-id="246e7-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="246e7-109">También puede buscar las consultas compartidas de forma pública en GitHub.</span><span class="sxs-lookup"><span data-stu-id="246e7-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="246e7-110">Estas consultas le permitirán seguir rápidamente los escenarios específicos de búsqueda contra amenazas sin tener que escribir las consultas desde cero.</span><span class="sxs-lookup"><span data-stu-id="246e7-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagen de las consultas compartidas](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="246e7-112">Guardar, modificar y compartir la consulta</span><span class="sxs-lookup"><span data-stu-id="246e7-112">Save, modify, and share a query</span></span>
<span data-ttu-id="246e7-113">Puede guardar una consulta nueva o existente para que sólo sea accesible para usted o compartida con otros usuarios en su organización.</span><span class="sxs-lookup"><span data-stu-id="246e7-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="246e7-114">Crear o modificar una consulta.</span><span class="sxs-lookup"><span data-stu-id="246e7-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="246e7-115">Haga clic en **Euardar consulta** en el botón desplegable y seleccione **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="246e7-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="246e7-116">Escriba un nombre para la consulta.</span><span class="sxs-lookup"><span data-stu-id="246e7-116">Enter a name for the query.</span></span> 

   ![Imagen de una consulta guardada](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="246e7-118">Seleccione la carpeta en la que desea guardar la consulta.</span><span class="sxs-lookup"><span data-stu-id="246e7-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="246e7-119">**Consultas compartidas** — compartidas con todos los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="246e7-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="246e7-120">**Mis consultas** — accesibles sólo para usted.</span><span class="sxs-lookup"><span data-stu-id="246e7-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="246e7-121">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="246e7-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="246e7-122">Eliminar o cambiar el nombre de la consulta</span><span class="sxs-lookup"><span data-stu-id="246e7-122">Delete or rename a query</span></span>
1. <span data-ttu-id="246e7-123">Haga clic con el botón derecho en la consulta que desee cambiar o eliminar el nombre.</span><span class="sxs-lookup"><span data-stu-id="246e7-123">Right-click on a query you want to rename or delete.</span></span>

    ![Imagen de una consulta eliminada](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="246e7-125">Seleccione **Eliminar** y confirme su eliminación.</span><span class="sxs-lookup"><span data-stu-id="246e7-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="246e7-126">O seleccione **Cambiar el nombre** y proporcione un nombre nuevo para la consulta.</span><span class="sxs-lookup"><span data-stu-id="246e7-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="246e7-127">Crear un vínculo directo a una consulta</span><span class="sxs-lookup"><span data-stu-id="246e7-127">Create a direct link to a query</span></span>
<span data-ttu-id="246e7-128">Para generar un vínculo que abra la consulta directamente en el editor de consultas de caza avanzadas, finalice la consulta y seleccione **compartir vínculo**.</span><span class="sxs-lookup"><span data-stu-id="246e7-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="246e7-129">Acceder a las consultas en el repositorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="246e7-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="246e7-130">Los investigadores de la seguridad de Microsoft comparten regularmente las consultas de búsquedas avanzadas en un [repositorio público designado en GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="246e7-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="246e7-131">Este repositorio está abierto a contribuciones.</span><span class="sxs-lookup"><span data-stu-id="246e7-131">This repository is open to contributions.</span></span> <span data-ttu-id="246e7-132">Para contribuir, [únete a GitHub gratis](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="246e7-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="246e7-133">Los investigadores de la seguridad de Microsoft también proporcionan búsquedas avanzadas que puede ser utilizadas para buscar actividades e indicadores asociados a las amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="246e7-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="246e7-134">Estas consultas son proporcionadas en los informes del [análisis de amenazas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="246e7-134">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="246e7-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="246e7-135">Related topics</span></span>
- [<span data-ttu-id="246e7-136">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="246e7-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="246e7-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="246e7-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="246e7-138">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="246e7-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="246e7-139">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="246e7-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="246e7-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="246e7-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="246e7-141">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="246e7-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
