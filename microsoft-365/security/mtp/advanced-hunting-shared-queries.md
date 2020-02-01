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
ms.openlocfilehash: 6e5dd8d1d80d08ed808bc607fcc7aba8a390a9ca
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600317"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="707fa-105">Utilice las consultas compartidas en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="707fa-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="707fa-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="707fa-106">**Applies to:**</span></span>
- <span data-ttu-id="707fa-107">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="707fa-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="707fa-108">Las consultas en la [búsqueda avanzada](advanced-hunting-overview.md) pueden ser compartidas entre usuarios de la misma organización.</span><span class="sxs-lookup"><span data-stu-id="707fa-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="707fa-109">También puede buscar las consultas compartidas de forma pública en GitHub.</span><span class="sxs-lookup"><span data-stu-id="707fa-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="707fa-110">Estas consultas le permitirán seguir rápidamente los escenarios específicos de búsqueda contra amenazas sin tener que escribir las consultas desde cero.</span><span class="sxs-lookup"><span data-stu-id="707fa-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagen de las consultas compartidas](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="707fa-112">Guardar, modificar y compartir la consulta</span><span class="sxs-lookup"><span data-stu-id="707fa-112">Save, modify, and share a query</span></span>
<span data-ttu-id="707fa-113">Puede guardar una consulta nueva o existente para que sólo sea accesible para usted o compartida con otros usuarios en su organización.</span><span class="sxs-lookup"><span data-stu-id="707fa-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="707fa-114">Crear o modificar una consulta.</span><span class="sxs-lookup"><span data-stu-id="707fa-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="707fa-115">Haga clic en **Euardar consulta** en el botón desplegable y seleccione **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="707fa-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="707fa-116">Escriba un nombre para la consulta.</span><span class="sxs-lookup"><span data-stu-id="707fa-116">Enter a name for the query.</span></span> 

   ![Imagen de una consulta guardada](../images/advanced-hunting-save-query.png)

4. <span data-ttu-id="707fa-118">Seleccione la carpeta en la que desea guardar la consulta.</span><span class="sxs-lookup"><span data-stu-id="707fa-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="707fa-119">**Consultas compartidas** — compartidas con todos los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="707fa-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="707fa-120">**Mis consultas** — accesibles sólo para usted.</span><span class="sxs-lookup"><span data-stu-id="707fa-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="707fa-121">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="707fa-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="707fa-122">Eliminar o cambiar el nombre de la consulta</span><span class="sxs-lookup"><span data-stu-id="707fa-122">Delete or rename a query</span></span>
1. <span data-ttu-id="707fa-123">Haga clic con el botón derecho en la consulta que desee cambiar o eliminar el nombre.</span><span class="sxs-lookup"><span data-stu-id="707fa-123">Right-click on a query you want to rename or delete.</span></span>

    ![Imagen de una consulta eliminada](../images/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="707fa-125">Seleccione **Eliminar** y confirme su eliminación.</span><span class="sxs-lookup"><span data-stu-id="707fa-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="707fa-126">O seleccione **Cambiar el nombre** y proporcione un nombre nuevo para la consulta.</span><span class="sxs-lookup"><span data-stu-id="707fa-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="707fa-127">Acceder a las consultas en el repositorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="707fa-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="707fa-128">Los investigadores de la seguridad de Microsoft comparten regularmente las consultas de búsquedas avanzadas en un [repositorio público designado en GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="707fa-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="707fa-129">Este repositorio está abierto a contribuciones.</span><span class="sxs-lookup"><span data-stu-id="707fa-129">This repository is open to contributions.</span></span> <span data-ttu-id="707fa-130">Para contribuir, [únete a GitHub gratis](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="707fa-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="707fa-131">Los investigadores de la seguridad de Microsoft también proporcionan búsquedas avanzadas que puede ser utilizadas para buscar actividades e indicadores asociados a las amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="707fa-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="707fa-132">Estas consultas son proporcionadas en los informes del [análisis de amenazas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="707fa-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="707fa-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="707fa-133">Related topics</span></span>
- [<span data-ttu-id="707fa-134">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="707fa-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="707fa-135">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="707fa-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="707fa-136">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="707fa-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="707fa-137">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="707fa-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="707fa-138">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="707fa-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)