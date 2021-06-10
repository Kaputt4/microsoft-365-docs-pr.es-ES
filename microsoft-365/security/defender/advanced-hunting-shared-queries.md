---
title: Usar consultas compartidas en la búsqueda avanzada Microsoft 365 Defender
description: Inicie inmediatamente la protección contra amenazas a través de las consultas predefinidas y compartidas. Comparta sus consultas con el público o con su organización.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, repositorio de github, mis consultas, consultas compartidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952589"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="84077-105">Utilice las consultas compartidas en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="84077-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="84077-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="84077-106">**Applies to:**</span></span>
- <span data-ttu-id="84077-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84077-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="84077-108">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="84077-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="84077-109">Las consultas en la [búsqueda avanzada](advanced-hunting-overview.md) pueden ser compartidas entre usuarios de la misma organización.</span><span class="sxs-lookup"><span data-stu-id="84077-109">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="84077-110">También puede buscar las consultas compartidas de forma pública en GitHub.</span><span class="sxs-lookup"><span data-stu-id="84077-110">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="84077-111">Estas consultas le permitirán seguir rápidamente los escenarios específicos de búsqueda contra amenazas sin tener que escribir las consultas desde cero.</span><span class="sxs-lookup"><span data-stu-id="84077-111">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagen de las consultas compartidas](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="84077-113">Guardar, modificar y compartir la consulta</span><span class="sxs-lookup"><span data-stu-id="84077-113">Save, modify, and share a query</span></span>
<span data-ttu-id="84077-114">Puede guardar una consulta nueva o existente para que sólo sea accesible para usted o compartida con otros usuarios en su organización.</span><span class="sxs-lookup"><span data-stu-id="84077-114">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="84077-115">Crear o modificar una consulta.</span><span class="sxs-lookup"><span data-stu-id="84077-115">Create or modify a query.</span></span> 

2. <span data-ttu-id="84077-116">Haga clic en **Euardar consulta** en el botón desplegable y seleccione **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="84077-116">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="84077-117">Escriba un nombre para la consulta.</span><span class="sxs-lookup"><span data-stu-id="84077-117">Enter a name for the query.</span></span> 

   ![Imagen de una consulta guardada](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="84077-119">Seleccione la carpeta en la que desea guardar la consulta.</span><span class="sxs-lookup"><span data-stu-id="84077-119">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="84077-120">**Consultas compartidas** — compartidas con todos los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="84077-120">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="84077-121">**Mis consultas** — accesibles sólo para usted.</span><span class="sxs-lookup"><span data-stu-id="84077-121">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="84077-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="84077-122">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="84077-123">Eliminar o cambiar el nombre de la consulta</span><span class="sxs-lookup"><span data-stu-id="84077-123">Delete or rename a query</span></span>
1. <span data-ttu-id="84077-124">Haga clic con el botón derecho en la consulta que desee cambiar o eliminar el nombre.</span><span class="sxs-lookup"><span data-stu-id="84077-124">Right-click on a query you want to rename or delete.</span></span>

    ![Imagen de una consulta eliminada](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="84077-126">Seleccione **Eliminar** y confirme su eliminación.</span><span class="sxs-lookup"><span data-stu-id="84077-126">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="84077-127">O seleccione **Cambiar el nombre** y proporcione un nombre nuevo para la consulta.</span><span class="sxs-lookup"><span data-stu-id="84077-127">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="84077-128">Crear un vínculo directo a una consulta</span><span class="sxs-lookup"><span data-stu-id="84077-128">Create a direct link to a query</span></span>
<span data-ttu-id="84077-129">Para generar un vínculo que abra la consulta directamente en el editor de consultas de búsqueda avanzada, finalizar la consulta y seleccionar **Compartir vínculo**.</span><span class="sxs-lookup"><span data-stu-id="84077-129">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="84077-130">Acceder a las consultas en el repositorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="84077-130">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="84077-131">Los investigadores de la seguridad de Microsoft comparten regularmente las consultas de búsquedas avanzadas en un [repositorio público designado en GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="84077-131">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="84077-132">Este repositorio está abierto a contribuciones.</span><span class="sxs-lookup"><span data-stu-id="84077-132">This repository is open to contributions.</span></span> <span data-ttu-id="84077-133">Para contribuir, [únete a GitHub gratis](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="84077-133">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="84077-134">Los investigadores de la seguridad de Microsoft también proporcionan búsquedas avanzadas que puede ser utilizadas para buscar actividades e indicadores asociados a las amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="84077-134">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="84077-135">Estas consultas son proporcionadas en los informes del [análisis de amenazas](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="84077-135">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

>[!NOTE]
><span data-ttu-id="84077-136">Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="84077-136">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="84077-137">[Activa Microsoft 365 Defender para](m365d-enable.md) buscar amenazas con más orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="84077-137">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="84077-138">Puede mover los flujos de trabajo avanzados de búsqueda de Microsoft Defender para endpoint a Microsoft 365 Defender siguiendo los pasos descritos en Migrar consultas avanzadas de búsqueda desde [Microsoft Defender para endpoint](advanced-hunting-migrate-from-mde.md).</span><span class="sxs-lookup"><span data-stu-id="84077-138">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="84077-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="84077-139">Related topics</span></span>
- [<span data-ttu-id="84077-140">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="84077-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="84077-141">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="84077-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="84077-142">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="84077-142">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="84077-143">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="84077-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="84077-144">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="84077-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="84077-145">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="84077-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)