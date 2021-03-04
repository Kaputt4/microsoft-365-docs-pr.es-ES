---
title: Función FileProfile() en búsqueda avanzada para Microsoft 365 Defender
description: Obtenga información sobre cómo usar FileProfile() para enriquecer información sobre los archivos de los resultados avanzados de la consulta de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.openlocfilehash: f2e92967b8951cd0f5a3c394a537404db1d53819
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424028"
---
# <a name="fileprofile"></a><span data-ttu-id="94063-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="94063-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="94063-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="94063-105">**Applies to:**</span></span>
- <span data-ttu-id="94063-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94063-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="94063-107">La `FileProfile()` función es una función de enriquecimiento en búsqueda [avanzada](advanced-hunting-overview.md) que agrega los siguientes datos a los archivos encontrados por la consulta.</span><span class="sxs-lookup"><span data-stu-id="94063-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="94063-108">Columna</span><span class="sxs-lookup"><span data-stu-id="94063-108">Column</span></span> | <span data-ttu-id="94063-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="94063-109">Data type</span></span> | <span data-ttu-id="94063-110">Description</span><span class="sxs-lookup"><span data-stu-id="94063-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="94063-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="94063-111">SHA1</span></span> | <span data-ttu-id="94063-112">cadena</span><span class="sxs-lookup"><span data-stu-id="94063-112">string</span></span> | <span data-ttu-id="94063-113">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="94063-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="94063-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="94063-114">SHA256</span></span> | <span data-ttu-id="94063-115">string</span><span class="sxs-lookup"><span data-stu-id="94063-115">string</span></span> | <span data-ttu-id="94063-116">SHA-256 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="94063-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="94063-117">MD5</span><span class="sxs-lookup"><span data-stu-id="94063-117">MD5</span></span> | <span data-ttu-id="94063-118">string</span><span class="sxs-lookup"><span data-stu-id="94063-118">string</span></span> | <span data-ttu-id="94063-119">Hash MD5 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="94063-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="94063-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="94063-120">FileSize</span></span> | <span data-ttu-id="94063-121">entero</span><span class="sxs-lookup"><span data-stu-id="94063-121">int</span></span> | <span data-ttu-id="94063-122">Tamaño del archivo en bytes</span><span class="sxs-lookup"><span data-stu-id="94063-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="94063-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="94063-123">GlobalPrevalence</span></span> | <span data-ttu-id="94063-124">entero</span><span class="sxs-lookup"><span data-stu-id="94063-124">int</span></span> | <span data-ttu-id="94063-125">Número de instancias de la entidad observadas por Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="94063-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="94063-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="94063-126">GlobalFirstSeen</span></span> | <span data-ttu-id="94063-127">datetime</span><span class="sxs-lookup"><span data-stu-id="94063-127">datetime</span></span> | <span data-ttu-id="94063-128">Fecha y hora en que Microsoft observó por primera vez la entidad globalmente</span><span class="sxs-lookup"><span data-stu-id="94063-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="94063-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="94063-129">GlobalLastSeen</span></span> | <span data-ttu-id="94063-130">datetime</span><span class="sxs-lookup"><span data-stu-id="94063-130">datetime</span></span> | <span data-ttu-id="94063-131">Fecha y hora en que Microsoft observó por última vez la entidad globalmente</span><span class="sxs-lookup"><span data-stu-id="94063-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="94063-132">Firmante</span><span class="sxs-lookup"><span data-stu-id="94063-132">Signer</span></span> | <span data-ttu-id="94063-133">string</span><span class="sxs-lookup"><span data-stu-id="94063-133">string</span></span> | <span data-ttu-id="94063-134">Información sobre el firmante del archivo</span><span class="sxs-lookup"><span data-stu-id="94063-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="94063-135">Emisor</span><span class="sxs-lookup"><span data-stu-id="94063-135">Issuer</span></span> | <span data-ttu-id="94063-136">string</span><span class="sxs-lookup"><span data-stu-id="94063-136">string</span></span> | <span data-ttu-id="94063-137">Información sobre la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="94063-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="94063-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="94063-138">SignerHash</span></span> | <span data-ttu-id="94063-139">string</span><span class="sxs-lookup"><span data-stu-id="94063-139">string</span></span> | <span data-ttu-id="94063-140">Valor hash único que identifica el firmante</span><span class="sxs-lookup"><span data-stu-id="94063-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="94063-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="94063-141">IsCertificateValid</span></span> | <span data-ttu-id="94063-142">boolean</span><span class="sxs-lookup"><span data-stu-id="94063-142">boolean</span></span> | <span data-ttu-id="94063-143">Si el certificado usado para firmar el archivo es válido</span><span class="sxs-lookup"><span data-stu-id="94063-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="94063-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="94063-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="94063-145">boolean</span><span class="sxs-lookup"><span data-stu-id="94063-145">boolean</span></span> | <span data-ttu-id="94063-146">Indica si el firmante del certificado raíz es Microsoft</span><span class="sxs-lookup"><span data-stu-id="94063-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="94063-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="94063-147">IsExecutable</span></span> | <span data-ttu-id="94063-148">boolean</span><span class="sxs-lookup"><span data-stu-id="94063-148">boolean</span></span> | <span data-ttu-id="94063-149">Si el archivo es un archivo ejecutable portátil (PE)</span><span class="sxs-lookup"><span data-stu-id="94063-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="94063-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="94063-150">ThreatName</span></span> | <span data-ttu-id="94063-151">string</span><span class="sxs-lookup"><span data-stu-id="94063-151">string</span></span> | <span data-ttu-id="94063-152">Nombre de detección de cualquier malware u otras amenazas encontradas</span><span class="sxs-lookup"><span data-stu-id="94063-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="94063-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="94063-153">Publisher</span></span> | <span data-ttu-id="94063-154">string</span><span class="sxs-lookup"><span data-stu-id="94063-154">string</span></span> | <span data-ttu-id="94063-155">Nombre de la organización que publicó el archivo</span><span class="sxs-lookup"><span data-stu-id="94063-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="94063-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="94063-156">SoftwareName</span></span> | <span data-ttu-id="94063-157">cadena</span><span class="sxs-lookup"><span data-stu-id="94063-157">string</span></span> | <span data-ttu-id="94063-158">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="94063-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="94063-159">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94063-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="94063-160">Argumentos</span><span class="sxs-lookup"><span data-stu-id="94063-160">Arguments</span></span>

- <span data-ttu-id="94063-161">**x**—columna de id. de archivo para usar: `SHA1` , , o ; función usa si no se `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especifica</span><span class="sxs-lookup"><span data-stu-id="94063-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="94063-162">**y**—limite al número de registros que se enriquecerán, de 1 a 1000; función usa 100 si no se especifica</span><span class="sxs-lookup"><span data-stu-id="94063-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="94063-163">Las funciones de enriquecimiento mostrarán información adicional solo cuando estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="94063-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="94063-164">La disponibilidad de información es variada y depende de muchos factores.</span><span class="sxs-lookup"><span data-stu-id="94063-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="94063-165">Asegúrese de tener esto en cuenta al usar FileProfile() en las consultas o al crear detecciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="94063-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="94063-166">Para obtener los mejores resultados, se recomienda usar la función FileProfile() con SHA1.</span><span class="sxs-lookup"><span data-stu-id="94063-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="94063-167">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="94063-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="94063-168">Proyecte solo la columna SHA1 y enriquezcala</span><span class="sxs-lookup"><span data-stu-id="94063-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="94063-169">Enriquecer los primeros 500 registros y enumerar archivos de baja prevalencia</span><span class="sxs-lookup"><span data-stu-id="94063-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="94063-170">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="94063-170">Related topics</span></span>
- [<span data-ttu-id="94063-171">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="94063-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="94063-172">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="94063-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="94063-173">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="94063-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="94063-174">Obtener más ejemplos de consulta</span><span class="sxs-lookup"><span data-stu-id="94063-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
