---
title: Establecer la configuración de búsqueda y análisis
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
ms.openlocfilehash: 5aa83f4f736c239b1cdfe940f27cfaa4b981ff64
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37092021"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="918cc-102">Establecer la configuración de búsqueda y análisis</span><span class="sxs-lookup"><span data-stu-id="918cc-102">Configure search and analytics settings</span></span>


## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="918cc-103">Duplicación cercana y subprocesamiento de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="918cc-103">Near duplicates and email threading</span></span>

<span data-ttu-id="918cc-104">En esta sección, puede establecer parámetros para la detección de duplicados, la detección de mensajes casi duplicados y el hilo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="918cc-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="918cc-105">Habilitar/deshabilitar: incluir detección de duplicados, detección de duplicados y subproceso de correo electrónico como parte del flujo de análisis si está habilitado.</span><span class="sxs-lookup"><span data-stu-id="918cc-105">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="918cc-106">Debido a que se basan en la otra parte, debe habilitarlas todas o deshabilitarlas todas.</span><span class="sxs-lookup"><span data-stu-id="918cc-106">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="918cc-107">Umbral: Si el nivel de similitud de dos documentos está por encima del umbral, se colocarán en el mismo conjunto Near duplicado.</span><span class="sxs-lookup"><span data-stu-id="918cc-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="918cc-108">Ocultar duplicados de manera predeterminada: Si esta configuración está activada, se aplicará un filtro para ocultar los documentos duplicados en el conjunto de revisiones de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="918cc-108">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the review set by default.</span></span> <span data-ttu-id="918cc-109">Si es necesario, el filtro se puede quitar manualmente en la revisión establecida.</span><span class="sxs-lookup"><span data-stu-id="918cc-109">The filter can be removed manually in the review set if necessary.</span></span>

- <span data-ttu-id="918cc-110">Número mínimo o máximo de palabras: las próximas duplicaciones y el procesamiento de correo electrónico se ejecutarán solo en los documentos que tengan al menos el número mínimo de palabras y el número máximo de palabras como máximo.</span><span class="sxs-lookup"><span data-stu-id="918cc-110">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>
<span data-ttu-id="918cc-111">Para obtener más información, vea cerca de la [detección de duplicados](near-duplicates.md) y el [procesamiento de correo electrónico](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="918cc-111">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="918cc-112">Temas</span><span class="sxs-lookup"><span data-stu-id="918cc-112">Themes</span></span>

<span data-ttu-id="918cc-113">En esta sección, puede establecer parámetros para los temas.</span><span class="sxs-lookup"><span data-stu-id="918cc-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="918cc-114">Habilitar/deshabilitar: incluir temas agrupados en clústeres como parte del flujo de análisis si está habilitado.</span><span class="sxs-lookup"><span data-stu-id="918cc-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="918cc-115">Ajustar el número máximo de temas dinámicamente dinámicamente: en algunos casos, no hay documentos suficientes para generar el número deseado de temas.</span><span class="sxs-lookup"><span data-stu-id="918cc-115">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="918cc-116">Si esta opción está activada, en lugar de intentar forzar el número máximo deseado de temas, el sistema ajusta dinámicamente el número máximo de temas.</span><span class="sxs-lookup"><span data-stu-id="918cc-116">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="918cc-117">Número máximo de temas: número deseado de temas</span><span class="sxs-lookup"><span data-stu-id="918cc-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="918cc-118">Incluir números en los temas: cuando está habilitado, incluirá los números en al generar los temas.</span><span class="sxs-lookup"><span data-stu-id="918cc-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="918cc-119">Reconocimiento óptico de caracteres (OCR)</span><span class="sxs-lookup"><span data-stu-id="918cc-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="918cc-120">Cuando esta opción está activada, OCR se ejecutará en las imágenes que se insertan en los conjuntos de revisiones para que puedan buscarse.</span><span class="sxs-lookup"><span data-stu-id="918cc-120">When this setting is turned on, OCR will be run on images that are ingested into review sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="918cc-121">Omitir texto</span><span class="sxs-lookup"><span data-stu-id="918cc-121">Ignore text</span></span>

<span data-ttu-id="918cc-122">Hay casos en los que determinados textos reducirán la calidad de los análisis, como las declinaciones de declinación de responsabilidad que se agregan a determinados mensajes de correo electrónico independientemente del contenido del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="918cc-122">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="918cc-123">Si tiene constancia de estos casos, puede excluir este texto de análisis especificando el texto (se admite RegEx) y los módulos a los que se debe excluir el texto.</span><span class="sxs-lookup"><span data-stu-id="918cc-123">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>