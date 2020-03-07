---
title: Analizar datos en un conjunto de revisión en eDiscovery avanzado
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
description: ''
ms.openlocfilehash: 0f9cb386ce57d6581ade5caa05e029511100d9b3
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42556788"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="fd58e-102">Analizar datos en un conjunto de revisión en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="fd58e-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="fd58e-103">Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos.</span><span class="sxs-lookup"><span data-stu-id="fd58e-103">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="fd58e-104">EDiscovery avanzado proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se van a revisar sin ninguna pérdida de información y para ayudarle a organizar los documentos de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="fd58e-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="fd58e-105">Para obtener más información acerca de estas funciones, consulte:</span><span class="sxs-lookup"><span data-stu-id="fd58e-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="fd58e-106">Detección de semiduplicados</span><span class="sxs-lookup"><span data-stu-id="fd58e-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="fd58e-107">Subprocesos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="fd58e-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="fd58e-108">Temas</span><span class="sxs-lookup"><span data-stu-id="fd58e-108">Themes</span></span>](themes.md)

<span data-ttu-id="fd58e-109">Para analizar los datos de un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="fd58e-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="fd58e-110">Configure las opciones de análisis en su caso.</span><span class="sxs-lookup"><span data-stu-id="fd58e-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="fd58e-111">Para obtener más información, vea [Configure Search and Analytics Settings](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fd58e-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="fd58e-112">Abra el conjunto de revisiones que desee analizar.</span><span class="sxs-lookup"><span data-stu-id="fd58e-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="fd58e-113">Haga clic en **administrar conjunto de revisiones**.</span><span class="sxs-lookup"><span data-stu-id="fd58e-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="fd58e-114">Haga clic en **ejecutar análisis para el conjunto de revisión**.</span><span class="sxs-lookup"><span data-stu-id="fd58e-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="fd58e-115">Puede comprobar el progreso del análisis en la ficha **trabajos** del caso.</span><span class="sxs-lookup"><span data-stu-id="fd58e-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="fd58e-116">Una vez completado el análisis, puede ver el informe de análisis, ejecutar consultas dentro de su conjunto de revisión en los resultados del análisis (vea la [consulta dentro del conjunto de revisión](review-set-search.md)) y ver los documentos relacionados de un documento determinado (vea [revisar los datos en el conjunto de revisiones](reviewing-data-in-review-set.md)).</span><span class="sxs-lookup"><span data-stu-id="fd58e-116">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="fd58e-117">Informe de análisis</span><span class="sxs-lookup"><span data-stu-id="fd58e-117">Analytics report</span></span>

<span data-ttu-id="fd58e-118">Para ver un informe de análisis de un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="fd58e-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="fd58e-119">Abra el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fd58e-119">Open the review set.</span></span>

2. <span data-ttu-id="fd58e-120">Haga clic en **administrar conjunto de revisiones**.</span><span class="sxs-lookup"><span data-stu-id="fd58e-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="fd58e-121">Haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="fd58e-121">Click **View report**.</span></span>

<span data-ttu-id="fd58e-122">El informe tiene siete componentes del análisis:</span><span class="sxs-lookup"><span data-stu-id="fd58e-122">The report has seven components from analysis:</span></span>

- <span data-ttu-id="fd58e-123">**Rellenado de destino:** El número de mensajes de correo electrónico, datos adjuntos y documentos sueltos que se encuentran en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fd58e-123">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="fd58e-124">**Documentos (sin datos adjuntos):** El número de documentos sueltos que son dinámicos, únicos Near duplicados de un pivote o un duplicado exacto de otro documento.</span><span class="sxs-lookup"><span data-stu-id="fd58e-124">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="fd58e-125">**Mensajes de correo electrónico:** El número de mensajes de correo electrónico que son inclusivos, copias inclusivas, menos inclusivas o ninguna de las anteriores.</span><span class="sxs-lookup"><span data-stu-id="fd58e-125">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="fd58e-126">**Datos adjuntos:** El número de datos adjuntos de correo electrónico que son únicos o duplicados de otro correo electrónico adjunto en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fd58e-126">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="fd58e-127">**Número de archivos por tipo:** El número de archivos, identificados por extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="fd58e-127">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="fd58e-128">**Documentos por origen:** Un resumen del contenido por su origen de datos original.</span><span class="sxs-lookup"><span data-stu-id="fd58e-128">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="fd58e-129">**Documentos agregados por proceso:** Un resumen del contenido de los procesos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fd58e-129">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
