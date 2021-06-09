---
title: Analizar datos en un conjunto de revisión en Advanced eDiscovery
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
description: Obtenga información sobre las herramientas disponibles para organizar conjuntos de documentos al analizar un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751375"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="07397-103">Analizar datos en un conjunto de revisión en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="07397-103">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="07397-104">Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos.</span><span class="sxs-lookup"><span data-stu-id="07397-104">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="07397-105">Advanced eDiscovery proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se revisarán sin pérdida de información y para ayudarle a organizar los documentos de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="07397-105">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="07397-106">Para obtener más información sobre estas funcionalidades, vea:</span><span class="sxs-lookup"><span data-stu-id="07397-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="07397-107">Detección de semiduplicados</span><span class="sxs-lookup"><span data-stu-id="07397-107">Near duplicate detection</span></span>](near-duplicate-detection-in-advanced-ediscovery.md)

- [<span data-ttu-id="07397-108">Subprocesos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="07397-108">Email threading</span></span>](email-threading-in-advanced-ediscovery.md)

- [<span data-ttu-id="07397-109">Temas</span><span class="sxs-lookup"><span data-stu-id="07397-109">Themes</span></span>](themes-in-advanced-ediscovery.md)

<span data-ttu-id="07397-110">Para analizar los datos de un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="07397-110">To analyze data in a review set:</span></span>

1. <span data-ttu-id="07397-111">Configure las opciones de análisis para su caso.</span><span class="sxs-lookup"><span data-stu-id="07397-111">Configure analytics settings for your case.</span></span> <span data-ttu-id="07397-112">Para obtener más información, vea [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="07397-112">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md).</span></span>

2. <span data-ttu-id="07397-113">Abra el conjunto de revisión que desea analizar.</span><span class="sxs-lookup"><span data-stu-id="07397-113">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="07397-114">Haga clic **en Administrar conjunto de revisión**.</span><span class="sxs-lookup"><span data-stu-id="07397-114">Click **Manage review set**.</span></span>

4. <span data-ttu-id="07397-115">Haga **clic en Ejecutar análisis para el conjunto de revisión**.</span><span class="sxs-lookup"><span data-stu-id="07397-115">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="07397-116">Puede comprobar el progreso del análisis en la **pestaña Trabajos** del caso.</span><span class="sxs-lookup"><span data-stu-id="07397-116">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="07397-117">Una vez completado el análisis, puede ver el informe de análisis, ejecutar consultas dentro del conjunto de revisión en los resultados del análisis (vea [Consulta](review-set-search.md)dentro del conjunto de revisión) y ver documentos relacionados de un documento determinado (vea [Revisión](reviewing-data-in-review-set.md)de datos en el conjunto de revisión).</span><span class="sxs-lookup"><span data-stu-id="07397-117">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="07397-118">Informe de análisis</span><span class="sxs-lookup"><span data-stu-id="07397-118">Analytics report</span></span>

<span data-ttu-id="07397-119">Para ver un informe de análisis para un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="07397-119">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="07397-120">Abra el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="07397-120">Open the review set.</span></span>

2. <span data-ttu-id="07397-121">Haga clic **en Administrar conjunto de revisión**.</span><span class="sxs-lookup"><span data-stu-id="07397-121">Click **Manage review set**.</span></span>

3. <span data-ttu-id="07397-122">Haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="07397-122">Click **View report**.</span></span>

<span data-ttu-id="07397-123">El informe tiene siete componentes del análisis:</span><span class="sxs-lookup"><span data-stu-id="07397-123">The report has seven components from analysis:</span></span>

- <span data-ttu-id="07397-124">**Población objetivo:** Número de mensajes de correo electrónico, datos adjuntos y documentos sueltos que se encuentran en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="07397-124">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="07397-125">**Documentos (excluyendo datos adjuntos):** El número de documentos sueltos que son pivotes, únicos casi duplicados de un elemento dinámico o un duplicado exacto de otro documento.</span><span class="sxs-lookup"><span data-stu-id="07397-125">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="07397-126">**Correos electrónicos:** El número de mensajes de correo electrónico que son inclusivos, copias inclusivas, menos incluidos o ninguno de los anteriores.</span><span class="sxs-lookup"><span data-stu-id="07397-126">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="07397-127">**Datos adjuntos:** Número de datos adjuntos de correo electrónico que son únicos o duplicados de otros datos adjuntos de correo electrónico en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="07397-127">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="07397-128">**Número de archivos por tipo:** El número de archivos, identificados por extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="07397-128">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="07397-129">**Documentos por origen:** Un resumen del contenido por su origen de datos original.</span><span class="sxs-lookup"><span data-stu-id="07397-129">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="07397-130">**Documentos agregados por proceso:** Un resumen del contenido mediante procesos de conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="07397-130">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
