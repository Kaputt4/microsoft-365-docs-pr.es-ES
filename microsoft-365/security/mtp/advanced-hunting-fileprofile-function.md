---
title: Función FileProfile() en la búsqueda avanzada para Microsoft 365 Defender
description: Obtenga información sobre cómo usar FileProfile() para enriquecer información sobre archivos en los resultados de consulta de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929555"
---
# <a name="fileprofile"></a><span data-ttu-id="be385-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="be385-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="be385-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="be385-105">**Applies to:**</span></span>
- <span data-ttu-id="be385-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be385-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="be385-107">La función es una función de enriquecimiento en la búsqueda avanzada que agrega los siguientes datos a `FileProfile()` los archivos encontrados por la consulta. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="be385-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="be385-108">Columna</span><span class="sxs-lookup"><span data-stu-id="be385-108">Column</span></span> | <span data-ttu-id="be385-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="be385-109">Data type</span></span> | <span data-ttu-id="be385-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="be385-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="be385-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="be385-111">SHA1</span></span> | <span data-ttu-id="be385-112">cadena</span><span class="sxs-lookup"><span data-stu-id="be385-112">string</span></span> | <span data-ttu-id="be385-113">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="be385-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="be385-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="be385-114">SHA256</span></span> | <span data-ttu-id="be385-115">string</span><span class="sxs-lookup"><span data-stu-id="be385-115">string</span></span> | <span data-ttu-id="be385-116">SHA-256 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="be385-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="be385-117">MD5</span><span class="sxs-lookup"><span data-stu-id="be385-117">MD5</span></span> | <span data-ttu-id="be385-118">string</span><span class="sxs-lookup"><span data-stu-id="be385-118">string</span></span> | <span data-ttu-id="be385-119">Hash MD5 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="be385-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="be385-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="be385-120">FileSize</span></span> | <span data-ttu-id="be385-121">entero</span><span class="sxs-lookup"><span data-stu-id="be385-121">int</span></span> | <span data-ttu-id="be385-122">Tamaño del archivo en bytes</span><span class="sxs-lookup"><span data-stu-id="be385-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="be385-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="be385-123">GlobalPrevalence</span></span> | <span data-ttu-id="be385-124">entero</span><span class="sxs-lookup"><span data-stu-id="be385-124">int</span></span> | <span data-ttu-id="be385-125">Número de instancias de la entidad observadas por Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="be385-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="be385-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="be385-126">GlobalFirstSeen</span></span> | <span data-ttu-id="be385-127">datetime</span><span class="sxs-lookup"><span data-stu-id="be385-127">datetime</span></span> | <span data-ttu-id="be385-128">Fecha y hora en que Microsoft observó por primera vez la entidad globalmente</span><span class="sxs-lookup"><span data-stu-id="be385-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="be385-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="be385-129">GlobalLastSeen</span></span> | <span data-ttu-id="be385-130">datetime</span><span class="sxs-lookup"><span data-stu-id="be385-130">datetime</span></span> | <span data-ttu-id="be385-131">Fecha y hora en que Microsoft observó la entidad por última vez globalmente</span><span class="sxs-lookup"><span data-stu-id="be385-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="be385-132">Firmante</span><span class="sxs-lookup"><span data-stu-id="be385-132">Signer</span></span> | <span data-ttu-id="be385-133">string</span><span class="sxs-lookup"><span data-stu-id="be385-133">string</span></span> | <span data-ttu-id="be385-134">Información sobre el firmante del archivo</span><span class="sxs-lookup"><span data-stu-id="be385-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="be385-135">Emisor</span><span class="sxs-lookup"><span data-stu-id="be385-135">Issuer</span></span> | <span data-ttu-id="be385-136">string</span><span class="sxs-lookup"><span data-stu-id="be385-136">string</span></span> | <span data-ttu-id="be385-137">Información sobre la entidad de certificación (CA) emisora</span><span class="sxs-lookup"><span data-stu-id="be385-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="be385-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="be385-138">SignerHash</span></span> | <span data-ttu-id="be385-139">string</span><span class="sxs-lookup"><span data-stu-id="be385-139">string</span></span> | <span data-ttu-id="be385-140">Valor hash único que identifica al firmante</span><span class="sxs-lookup"><span data-stu-id="be385-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="be385-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="be385-141">IsCertificateValid</span></span> | <span data-ttu-id="be385-142">boolean</span><span class="sxs-lookup"><span data-stu-id="be385-142">boolean</span></span> | <span data-ttu-id="be385-143">Si el certificado usado para firmar el archivo es válido</span><span class="sxs-lookup"><span data-stu-id="be385-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="be385-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="be385-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="be385-145">boolean</span><span class="sxs-lookup"><span data-stu-id="be385-145">boolean</span></span> | <span data-ttu-id="be385-146">Indica si el firmante del certificado raíz es Microsoft</span><span class="sxs-lookup"><span data-stu-id="be385-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="be385-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="be385-147">IsExecutable</span></span> | <span data-ttu-id="be385-148">boolean</span><span class="sxs-lookup"><span data-stu-id="be385-148">boolean</span></span> | <span data-ttu-id="be385-149">Si el archivo es un archivo portable ejecutable (PE)</span><span class="sxs-lookup"><span data-stu-id="be385-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="be385-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="be385-150">ThreatName</span></span> | <span data-ttu-id="be385-151">string</span><span class="sxs-lookup"><span data-stu-id="be385-151">string</span></span> | <span data-ttu-id="be385-152">Nombre de la detección de cualquier malware u otras amenazas encontradas</span><span class="sxs-lookup"><span data-stu-id="be385-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="be385-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="be385-153">Publisher</span></span> | <span data-ttu-id="be385-154">string</span><span class="sxs-lookup"><span data-stu-id="be385-154">string</span></span> | <span data-ttu-id="be385-155">Nombre de la organización que publicó el archivo</span><span class="sxs-lookup"><span data-stu-id="be385-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="be385-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="be385-156">SoftwareName</span></span> | <span data-ttu-id="be385-157">cadena</span><span class="sxs-lookup"><span data-stu-id="be385-157">string</span></span> | <span data-ttu-id="be385-158">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="be385-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="be385-159">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be385-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="be385-160">Argumentos</span><span class="sxs-lookup"><span data-stu-id="be385-160">Arguments</span></span>

- <span data-ttu-id="be385-161">**x**: columna de id. de archivo que se usa: `SHA1` , , o ; la función usa si no se `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especifica</span><span class="sxs-lookup"><span data-stu-id="be385-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="be385-162">**y:** límite al número de registros que se enriquecerán, de 1 a 1000; usa 100 si no se especifica</span><span class="sxs-lookup"><span data-stu-id="be385-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="be385-163">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="be385-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="be385-164">Proyectar solo la columna SHA1 y enriquecer</span><span class="sxs-lookup"><span data-stu-id="be385-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="be385-165">Enriquecer los primeros 500 registros y enumerar archivos de baja prevalencia</span><span class="sxs-lookup"><span data-stu-id="be385-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="be385-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="be385-166">Related topics</span></span>
- [<span data-ttu-id="be385-167">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="be385-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="be385-168">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="be385-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="be385-169">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="be385-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="be385-170">Obtener más ejemplos de consulta</span><span class="sxs-lookup"><span data-stu-id="be385-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
