---
title: 'Configurar las opciones de búsqueda y análisis: investigaciones de datos'
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
description: Obtenga información sobre cómo configurar las opciones de búsqueda y análisis, como duplicados Near, subprocesos de correo electrónico y temas al administrar investigaciones de datos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3100c83fc027e793f7937a4d27e059ce7e3038a0
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527356"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="9c419-103">Establecer la configuración de búsqueda y análisis</span><span class="sxs-lookup"><span data-stu-id="9c419-103">Configure search and analytics settings</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="9c419-104">Duplicación cercana y subprocesamiento de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="9c419-104">Near duplicates and email threading</span></span>

<span data-ttu-id="9c419-105">En esta sección, puede establecer parámetros para la detección de duplicados, la detección de mensajes casi duplicados y el hilo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9c419-105">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="9c419-106">Habilitar/deshabilitar: incluir detección de duplicados, detección de duplicados y subproceso de correo electrónico como parte del flujo de análisis si está habilitado.</span><span class="sxs-lookup"><span data-stu-id="9c419-106">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="9c419-107">Debido a que se basan en la otra parte, debe habilitarlas todas o deshabilitarlas todas.</span><span class="sxs-lookup"><span data-stu-id="9c419-107">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="9c419-108">Umbral: Si el nivel de similitud de dos documentos está por encima del umbral, se colocarán en el mismo conjunto Near duplicado.</span><span class="sxs-lookup"><span data-stu-id="9c419-108">Threshold: if the similarity level of two documents is above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="9c419-109">Ocultar duplicados de manera predeterminada: Si esta configuración está activada, se aplicará un filtro para ocultar los documentos duplicados en el conjunto de trabajo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9c419-109">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="9c419-110">Si es necesario, el filtro se puede quitar manualmente en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9c419-110">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="9c419-111">Número mínimo o máximo de palabras: las próximas duplicaciones y el procesamiento de correo electrónico se ejecutarán solo en los documentos que tengan al menos el número mínimo de palabras y el número máximo de palabras como máximo.</span><span class="sxs-lookup"><span data-stu-id="9c419-111">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>

<span data-ttu-id="9c419-112">Para obtener más información, vea cerca de la [detección de duplicados](near-duplicates.md) y el [procesamiento de correo electrónico](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="9c419-112">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="9c419-113">Temas</span><span class="sxs-lookup"><span data-stu-id="9c419-113">Themes</span></span>

<span data-ttu-id="9c419-114">En esta sección, puede establecer parámetros para los temas.</span><span class="sxs-lookup"><span data-stu-id="9c419-114">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="9c419-115">Habilitar/deshabilitar: incluir temas agrupados en clústeres como parte del flujo de análisis si está habilitado.</span><span class="sxs-lookup"><span data-stu-id="9c419-115">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>

- <span data-ttu-id="9c419-116">Ajustar el número máximo de temas dinámicamente: en algunos casos, no hay documentos suficientes para producir el número de temas deseado.</span><span class="sxs-lookup"><span data-stu-id="9c419-116">Adjust maximum number of themes dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="9c419-117">Si esta opción está activada, en lugar de intentar forzar el número máximo deseado de temas, el sistema ajusta dinámicamente el número máximo de temas.</span><span class="sxs-lookup"><span data-stu-id="9c419-117">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>

- <span data-ttu-id="9c419-118">Número máximo de temas: número deseado de temas.</span><span class="sxs-lookup"><span data-stu-id="9c419-118">Maximum number of themes: desired number of themes.</span></span>

- <span data-ttu-id="9c419-119">Incluir números en los temas: cuando está habilitado, incluirá los números en al generar los temas.</span><span class="sxs-lookup"><span data-stu-id="9c419-119">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="9c419-120">Reconocimiento óptico de caracteres (OCR)</span><span class="sxs-lookup"><span data-stu-id="9c419-120">Optical character recognition (OCR)</span></span>

<span data-ttu-id="9c419-121">Cuando esta opción está activada, OCR se ejecutará en las imágenes que se insertan en los conjuntos de trabajo para que se puedan buscar.</span><span class="sxs-lookup"><span data-stu-id="9c419-121">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="9c419-122">Omitir texto</span><span class="sxs-lookup"><span data-stu-id="9c419-122">Ignore text</span></span>

<span data-ttu-id="9c419-123">Hay casos en los que determinados textos reducirán la calidad de los análisis, como las declinaciones de declinación de responsabilidad que se agregan a determinados mensajes de correo electrónico independientemente del contenido del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9c419-123">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="9c419-124">Si tiene constancia de estos casos, puede excluir este texto de análisis especificando el texto (se admite RegEx) y los módulos a los que se debe excluir el texto.</span><span class="sxs-lookup"><span data-stu-id="9c419-124">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>
