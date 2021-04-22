---
title: Función FileProfile() en búsqueda avanzada para Microsoft 365 Defender
description: Obtenga información sobre cómo usar FileProfile() para enriquecer información sobre los archivos de los resultados avanzados de la consulta de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.openlocfilehash: 67295529cdb7b8a3e93e663f2a8a28d27a8f6737
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935850"
---
# <a name="fileprofile"></a><span data-ttu-id="89e30-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="89e30-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="89e30-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="89e30-105">**Applies to:**</span></span>
- <span data-ttu-id="89e30-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89e30-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="89e30-107">La `FileProfile()` función es una función de enriquecimiento en búsqueda [avanzada](advanced-hunting-overview.md) que agrega los siguientes datos a los archivos encontrados por la consulta.</span><span class="sxs-lookup"><span data-stu-id="89e30-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="89e30-108">Column</span><span class="sxs-lookup"><span data-stu-id="89e30-108">Column</span></span> | <span data-ttu-id="89e30-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="89e30-109">Data type</span></span> | <span data-ttu-id="89e30-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="89e30-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="89e30-111">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-111">string</span></span> | <span data-ttu-id="89e30-112">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="89e30-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="89e30-113">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-113">string</span></span> | <span data-ttu-id="89e30-114">SHA-256 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="89e30-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="89e30-115">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-115">string</span></span> | <span data-ttu-id="89e30-116">Hash MD5 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="89e30-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="89e30-117">Entero</span><span class="sxs-lookup"><span data-stu-id="89e30-117">int</span></span> | <span data-ttu-id="89e30-118">Tamaño del archivo en bytes</span><span class="sxs-lookup"><span data-stu-id="89e30-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="89e30-119">Entero</span><span class="sxs-lookup"><span data-stu-id="89e30-119">int</span></span> | <span data-ttu-id="89e30-120">Número de instancias de la entidad observadas por Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="89e30-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="89e30-121">datetime</span><span class="sxs-lookup"><span data-stu-id="89e30-121">datetime</span></span> | <span data-ttu-id="89e30-122">Fecha y hora en que Microsoft observó por primera vez la entidad globalmente</span><span class="sxs-lookup"><span data-stu-id="89e30-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="89e30-123">datetime</span><span class="sxs-lookup"><span data-stu-id="89e30-123">datetime</span></span> | <span data-ttu-id="89e30-124">Fecha y hora en que Microsoft observó por última vez la entidad globalmente</span><span class="sxs-lookup"><span data-stu-id="89e30-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="89e30-125">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-125">string</span></span> | <span data-ttu-id="89e30-126">Información sobre el firmante del archivo</span><span class="sxs-lookup"><span data-stu-id="89e30-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="89e30-127">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-127">string</span></span> | <span data-ttu-id="89e30-128">Información sobre la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="89e30-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="89e30-129">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-129">string</span></span> | <span data-ttu-id="89e30-130">Valor hash único que identifica el firmante</span><span class="sxs-lookup"><span data-stu-id="89e30-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="89e30-131">boolean</span><span class="sxs-lookup"><span data-stu-id="89e30-131">boolean</span></span> | <span data-ttu-id="89e30-132">Si el certificado usado para firmar el archivo es válido</span><span class="sxs-lookup"><span data-stu-id="89e30-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="89e30-133">boolean</span><span class="sxs-lookup"><span data-stu-id="89e30-133">boolean</span></span> | <span data-ttu-id="89e30-134">Indica si el firmante del certificado raíz es Microsoft</span><span class="sxs-lookup"><span data-stu-id="89e30-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="89e30-135">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-135">string</span></span> | <span data-ttu-id="89e30-136">Estado de la firma del archivo: SignedValid : el archivo está firmado con una firma válida, SignedInvalid - el archivo está firmado pero el certificado no es válido, No firmado - el archivo no está firmado, Desconocido - la información sobre el archivo no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="89e30-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="89e30-137">boolean</span><span class="sxs-lookup"><span data-stu-id="89e30-137">boolean</span></span> | <span data-ttu-id="89e30-138">Si el archivo es un archivo ejecutable portátil (PE)</span><span class="sxs-lookup"><span data-stu-id="89e30-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="89e30-139">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-139">string</span></span> | <span data-ttu-id="89e30-140">Nombre de detección de cualquier malware u otras amenazas encontradas</span><span class="sxs-lookup"><span data-stu-id="89e30-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="89e30-141">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-141">string</span></span> | <span data-ttu-id="89e30-142">Nombre de la organización que publicó el archivo</span><span class="sxs-lookup"><span data-stu-id="89e30-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="89e30-143">cadena</span><span class="sxs-lookup"><span data-stu-id="89e30-143">string</span></span> | <span data-ttu-id="89e30-144">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="89e30-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="89e30-145">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89e30-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="89e30-146">Argumentos</span><span class="sxs-lookup"><span data-stu-id="89e30-146">Arguments</span></span>

- <span data-ttu-id="89e30-147">**x**—columna de id. de archivo para usar: `SHA1` , , o ; función usa si no se `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especifica</span><span class="sxs-lookup"><span data-stu-id="89e30-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="89e30-148">**y**—limite al número de registros que se enriquecerán, de 1 a 1000; función usa 100 si no se especifica</span><span class="sxs-lookup"><span data-stu-id="89e30-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="89e30-149">Las funciones de enriquecimiento mostrarán información adicional solo cuando estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="89e30-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="89e30-150">La disponibilidad de información es variada y depende de muchos factores.</span><span class="sxs-lookup"><span data-stu-id="89e30-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="89e30-151">Asegúrese de tener esto en cuenta al usar FileProfile() en las consultas o al crear detecciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="89e30-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="89e30-152">Para obtener los mejores resultados, se recomienda usar la función FileProfile() con SHA1.</span><span class="sxs-lookup"><span data-stu-id="89e30-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="89e30-153">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="89e30-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="89e30-154">Proyecte solo la columna SHA1 y enriquezcala</span><span class="sxs-lookup"><span data-stu-id="89e30-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="89e30-155">Enriquecer los primeros 500 registros y enumerar archivos de baja prevalencia</span><span class="sxs-lookup"><span data-stu-id="89e30-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="89e30-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="89e30-156">Related topics</span></span>
- [<span data-ttu-id="89e30-157">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="89e30-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="89e30-158">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="89e30-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="89e30-159">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="89e30-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="89e30-160">Obtener más ejemplos de consulta</span><span class="sxs-lookup"><span data-stu-id="89e30-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
