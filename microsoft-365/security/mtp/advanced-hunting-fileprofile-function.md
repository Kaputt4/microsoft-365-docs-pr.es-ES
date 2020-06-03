---
title: La función FileProfile () en la caza avanzada para la protección contra amenazas de Microsoft
description: Obtenga información sobre cómo usar FileProfile () para enriquecer la información sobre los archivos en los resultados de la consulta de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.openlocfilehash: 039b9dc038cd1a1645aee2289f3bdb389eb3f426
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515941"
---
# <a name="fileprofile"></a><span data-ttu-id="16abc-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="16abc-104">FileProfile()</span></span>

<span data-ttu-id="16abc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="16abc-105">**Applies to:**</span></span>
- <span data-ttu-id="16abc-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="16abc-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="16abc-107">La `FileProfile()` función es una función de enriquecimiento de la [búsqueda avanzada](advanced-hunting-overview.md) que agrega los siguientes datos a los archivos encontrados por la consulta.</span><span class="sxs-lookup"><span data-stu-id="16abc-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="16abc-108">Columna</span><span class="sxs-lookup"><span data-stu-id="16abc-108">Column</span></span> | <span data-ttu-id="16abc-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="16abc-109">Data type</span></span> | <span data-ttu-id="16abc-110">Description</span><span class="sxs-lookup"><span data-stu-id="16abc-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="16abc-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="16abc-111">SHA1</span></span> | <span data-ttu-id="16abc-112">cadena</span><span class="sxs-lookup"><span data-stu-id="16abc-112">string</span></span> | <span data-ttu-id="16abc-113">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="16abc-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="16abc-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="16abc-114">SHA256</span></span> | <span data-ttu-id="16abc-115">string</span><span class="sxs-lookup"><span data-stu-id="16abc-115">string</span></span> | <span data-ttu-id="16abc-116">SHA-256 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="16abc-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="16abc-117">MD5</span><span class="sxs-lookup"><span data-stu-id="16abc-117">MD5</span></span> | <span data-ttu-id="16abc-118">string</span><span class="sxs-lookup"><span data-stu-id="16abc-118">string</span></span> | <span data-ttu-id="16abc-119">Hash MD5 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="16abc-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="16abc-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="16abc-120">FileSize</span></span> | <span data-ttu-id="16abc-121">Entero</span><span class="sxs-lookup"><span data-stu-id="16abc-121">int</span></span> | <span data-ttu-id="16abc-122">Tamaño del archivo en bytes</span><span class="sxs-lookup"><span data-stu-id="16abc-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="16abc-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="16abc-123">GlobalPrevalence</span></span> | <span data-ttu-id="16abc-124">Entero</span><span class="sxs-lookup"><span data-stu-id="16abc-124">int</span></span> | <span data-ttu-id="16abc-125">Número de instancias de la entidad observadas por Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="16abc-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="16abc-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="16abc-126">GlobalFirstSeen</span></span> | <span data-ttu-id="16abc-127">datetime</span><span class="sxs-lookup"><span data-stu-id="16abc-127">datetime</span></span> | <span data-ttu-id="16abc-128">Fecha y hora en que Microsoft observó por primera vez la entidad</span><span class="sxs-lookup"><span data-stu-id="16abc-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="16abc-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="16abc-129">GlobalLastSeen</span></span> | <span data-ttu-id="16abc-130">datetime</span><span class="sxs-lookup"><span data-stu-id="16abc-130">datetime</span></span> | <span data-ttu-id="16abc-131">Fecha y hora en que Microsoft recibió la última observación global de la entidad</span><span class="sxs-lookup"><span data-stu-id="16abc-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="16abc-132">Firmante</span><span class="sxs-lookup"><span data-stu-id="16abc-132">Signer</span></span> | <span data-ttu-id="16abc-133">string</span><span class="sxs-lookup"><span data-stu-id="16abc-133">string</span></span> | <span data-ttu-id="16abc-134">Información sobre el firmante del archivo</span><span class="sxs-lookup"><span data-stu-id="16abc-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="16abc-135">Emisor</span><span class="sxs-lookup"><span data-stu-id="16abc-135">Issuer</span></span> | <span data-ttu-id="16abc-136">string</span><span class="sxs-lookup"><span data-stu-id="16abc-136">string</span></span> | <span data-ttu-id="16abc-137">Información sobre la entidad de certificación (CA) emisora</span><span class="sxs-lookup"><span data-stu-id="16abc-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="16abc-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="16abc-138">SignerHash</span></span> | <span data-ttu-id="16abc-139">string</span><span class="sxs-lookup"><span data-stu-id="16abc-139">string</span></span> | <span data-ttu-id="16abc-140">Valor hash único que identifica al firmante</span><span class="sxs-lookup"><span data-stu-id="16abc-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="16abc-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="16abc-141">IsCertificateValid</span></span> | <span data-ttu-id="16abc-142">boolean</span><span class="sxs-lookup"><span data-stu-id="16abc-142">boolean</span></span> | <span data-ttu-id="16abc-143">Si el certificado usado para firmar el archivo es válido</span><span class="sxs-lookup"><span data-stu-id="16abc-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="16abc-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="16abc-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="16abc-145">boolean</span><span class="sxs-lookup"><span data-stu-id="16abc-145">boolean</span></span> | <span data-ttu-id="16abc-146">Indica si el firmante del certificado raíz es Microsoft</span><span class="sxs-lookup"><span data-stu-id="16abc-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="16abc-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="16abc-147">IsExecutable</span></span> | <span data-ttu-id="16abc-148">boolean</span><span class="sxs-lookup"><span data-stu-id="16abc-148">boolean</span></span> | <span data-ttu-id="16abc-149">Si el archivo es un archivo ejecutable portable (PE)</span><span class="sxs-lookup"><span data-stu-id="16abc-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="16abc-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="16abc-150">ThreatName</span></span> | <span data-ttu-id="16abc-151">string</span><span class="sxs-lookup"><span data-stu-id="16abc-151">string</span></span> | <span data-ttu-id="16abc-152">Nombre de detección de cualquier malware u otras amenazas encontradas</span><span class="sxs-lookup"><span data-stu-id="16abc-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="16abc-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="16abc-153">Publisher</span></span> | <span data-ttu-id="16abc-154">string</span><span class="sxs-lookup"><span data-stu-id="16abc-154">string</span></span> | <span data-ttu-id="16abc-155">Nombre de la organización que publicó el archivo</span><span class="sxs-lookup"><span data-stu-id="16abc-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="16abc-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="16abc-156">SoftwareName</span></span> | <span data-ttu-id="16abc-157">string</span><span class="sxs-lookup"><span data-stu-id="16abc-157">string</span></span> | <span data-ttu-id="16abc-158">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="16abc-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="16abc-159">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16abc-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="16abc-160">Argumentos</span><span class="sxs-lookup"><span data-stu-id="16abc-160">Arguments</span></span>

- <span data-ttu-id="16abc-161">**x** — columna de identificador de archivo que se debe usar: `SHA1` , `SHA256` `InitiatingProcessSHA1` o `InitiatingProcessSHA256` ; la función usa `SHA1` si no se especifica</span><span class="sxs-lookup"><span data-stu-id="16abc-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="16abc-162">**y** : límite para el número de registros para enriquecer, 1-1000; la función usa 100 si no se especifica</span><span class="sxs-lookup"><span data-stu-id="16abc-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="16abc-163">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="16abc-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="16abc-164">Proyectar sólo la columna SHA1 y enriquecerla</span><span class="sxs-lookup"><span data-stu-id="16abc-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="16abc-165">Enriquezca los primeros 500 registros y enumere los archivos de baja difusión</span><span class="sxs-lookup"><span data-stu-id="16abc-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="16abc-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="16abc-166">Related topics</span></span>
- [<span data-ttu-id="16abc-167">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="16abc-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="16abc-168">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="16abc-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="16abc-169">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="16abc-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)