---
title: Exportar datos de casos en eDiscovery avanzado
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
description: Obtenga información sobre cómo exportar o descargar contenido de un conjunto de revisiones para presentaciones o revisiones externas en un caso de exhibición avanzada de documentos electrónicos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 114264f342a51f3ce68696f321cf7c6e929dc6d1
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726477"
---
# <a name="export-case-data-in-advanced-ediscovery"></a><span data-ttu-id="1a102-103">Exportar datos de casos en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="1a102-103">Export case data in Advanced eDiscovery</span></span>

<span data-ttu-id="1a102-104">Hay tres formas de exportar datos de un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="1a102-104">There are three ways to export data from a review set:</span></span>

<span data-ttu-id="1a102-105">**Descargar:** Descargar (mediante un explorador) un pequeño conjunto de archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="1a102-105">**Download:** Download (by using a browser) a small set of native files.</span></span> <span data-ttu-id="1a102-106">Esta es la forma más rápida de exportar un pequeño conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="1a102-106">This is the quickest way to export a small set of data.</span></span> <span data-ttu-id="1a102-107">Este método conserva los nombres de archivo nativos.</span><span class="sxs-lookup"><span data-stu-id="1a102-107">This method preserves the native file names.</span></span>

<span data-ttu-id="1a102-108">**Exportar:** Personalizar qué datos se exportan.</span><span class="sxs-lookup"><span data-stu-id="1a102-108">**Export:** Customize what data is exported.</span></span> <span data-ttu-id="1a102-109">Esto incluye la exportación de metadatos de archivo, archivos nativos, archivos de texto y documentos redactados que se han guardado en un archivo PDF.</span><span class="sxs-lookup"><span data-stu-id="1a102-109">This includes exporting file metadata, native files, text files, and redacted documents that have been saved to a PDF file.</span></span> <span data-ttu-id="1a102-110">Después de cargar los datos exportados en una ubicación de almacenamiento de Azure, puede descargarlos en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="1a102-110">After the exported data is uploaded to an Azure Storage location, you can download it to a local computer.</span></span> <span data-ttu-id="1a102-111">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="1a102-111">For more information, see:</span></span>

- [<span data-ttu-id="1a102-112">Exportar documentos desde un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="1a102-112">Export documents from a review set</span></span>](export-documents-from-review-set.md)

- [<span data-ttu-id="1a102-113">Descargar trabajos de exportación</span><span class="sxs-lookup"><span data-stu-id="1a102-113">Download export jobs</span></span>](download-export-jobs.md)

<span data-ttu-id="1a102-114">**Agregar a otro conjunto de revisión:** Copiar datos de un conjunto de revisión a un conjunto de revisión diferente.</span><span class="sxs-lookup"><span data-stu-id="1a102-114">**Add to another review set:** Copy data from one review set to a different review set.</span></span> <span data-ttu-id="1a102-115">Para obtener más información, consulte [Agregar datos de un conjunto de revisión a otro conjunto de revisión](add-data-to-review-set-from-another-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="1a102-115">For more information, see [Add data from one review set to another review set](add-data-to-review-set-from-another-review-set.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1a102-116">En Microsoft 365, se aplica un algoritmo hash a los datos y esos hash se proporcionan en el archivo de salida con fines de comprobación.</span><span class="sxs-lookup"><span data-stu-id="1a102-116">In Microsoft 365, data is hashed and those hashes are provided in the output file for verification purposes.</span></span> <span data-ttu-id="1a102-117">Esto se complementa con la funcionalidad de informes y registros de auditoría, como estadísticas de recopilación, informes de carga y de informes de exportación (incluido el archivo de carga de exportación).</span><span class="sxs-lookup"><span data-stu-id="1a102-117">This is supplemented by audit logs and reporting functionality, such as collection statistics, load set reports, and export reports (including the export load file).</span></span>
