---
title: Función FileProfile() en búsqueda avanzada para Microsoft Defender para endpoint
description: Obtenga información sobre cómo usar FileProfile() para enriquecer información sobre los archivos de los resultados avanzados de la consulta de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, ATP de Microsoft Defender, Microsoft Defender para endpoint, Windows Defender, WINDOWS DEFENDER ATP, protección contra amenazas avanzada de Windows Defender, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076008"
---
# <a name="fileprofile"></a><span data-ttu-id="11b0a-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="11b0a-104">FileProfile()</span></span>

<span data-ttu-id="11b0a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="11b0a-105">**Applies to:**</span></span>
- [<span data-ttu-id="11b0a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="11b0a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

<span data-ttu-id="11b0a-107">La `FileProfile()` función es una función de enriquecimiento en búsqueda [avanzada](advanced-hunting-overview.md) que agrega los siguientes datos a los archivos encontrados por la consulta.</span><span class="sxs-lookup"><span data-stu-id="11b0a-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

<span data-ttu-id="11b0a-108">Column</span><span class="sxs-lookup"><span data-stu-id="11b0a-108">Column</span></span> | <span data-ttu-id="11b0a-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="11b0a-109">Data type</span></span> | <span data-ttu-id="11b0a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="11b0a-110">Description</span></span>
-|-|-
<span data-ttu-id="11b0a-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="11b0a-111">SHA1</span></span> | <span data-ttu-id="11b0a-112">cadena</span><span class="sxs-lookup"><span data-stu-id="11b0a-112">string</span></span> | <span data-ttu-id="11b0a-113">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="11b0a-113">SHA-1 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="11b0a-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="11b0a-114">SHA256</span></span> | <span data-ttu-id="11b0a-115">string</span><span class="sxs-lookup"><span data-stu-id="11b0a-115">string</span></span> | <span data-ttu-id="11b0a-116">SHA-256 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="11b0a-116">SHA-256 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="11b0a-117">MD5</span><span class="sxs-lookup"><span data-stu-id="11b0a-117">MD5</span></span> | <span data-ttu-id="11b0a-118">string</span><span class="sxs-lookup"><span data-stu-id="11b0a-118">string</span></span> | <span data-ttu-id="11b0a-119">Hash MD5 del archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="11b0a-119">MD5 hash of the file that the recorded action was applied to</span></span>
<span data-ttu-id="11b0a-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="11b0a-120">FileSize</span></span> | <span data-ttu-id="11b0a-121">Entero</span><span class="sxs-lookup"><span data-stu-id="11b0a-121">int</span></span> | <span data-ttu-id="11b0a-122">Tamaño del archivo en bytes</span><span class="sxs-lookup"><span data-stu-id="11b0a-122">Size of the file in bytes</span></span>
<span data-ttu-id="11b0a-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="11b0a-123">GlobalPrevalence</span></span> | <span data-ttu-id="11b0a-124">Entero</span><span class="sxs-lookup"><span data-stu-id="11b0a-124">int</span></span> | <span data-ttu-id="11b0a-125">Número de instancias de la entidad observadas por Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="11b0a-125">Number of instances of the entity observed by Microsoft globally</span></span>
<span data-ttu-id="11b0a-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="11b0a-126">GlobalFirstSeen</span></span> | <span data-ttu-id="11b0a-127">datetime</span><span class="sxs-lookup"><span data-stu-id="11b0a-127">datetime</span></span> | <span data-ttu-id="11b0a-128">Fecha y hora en que Microsoft observó por primera vez la entidad globalmente</span><span class="sxs-lookup"><span data-stu-id="11b0a-128">Date and time when the entity was first observed by Microsoft globally</span></span>
<span data-ttu-id="11b0a-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="11b0a-129">GlobalLastSeen</span></span> | <span data-ttu-id="11b0a-130">datetime</span><span class="sxs-lookup"><span data-stu-id="11b0a-130">datetime</span></span> | <span data-ttu-id="11b0a-131">Fecha y hora en que Microsoft observó por última vez la entidad globalmente</span><span class="sxs-lookup"><span data-stu-id="11b0a-131">Date and time when the entity was last observed by Microsoft globally</span></span>
<span data-ttu-id="11b0a-132">Firmante</span><span class="sxs-lookup"><span data-stu-id="11b0a-132">Signer</span></span> | <span data-ttu-id="11b0a-133">string</span><span class="sxs-lookup"><span data-stu-id="11b0a-133">string</span></span> | <span data-ttu-id="11b0a-134">Información sobre el firmante del archivo</span><span class="sxs-lookup"><span data-stu-id="11b0a-134">Information about the signer of the file</span></span>
<span data-ttu-id="11b0a-135">Emisor</span><span class="sxs-lookup"><span data-stu-id="11b0a-135">Issuer</span></span> | <span data-ttu-id="11b0a-136">string</span><span class="sxs-lookup"><span data-stu-id="11b0a-136">string</span></span> | <span data-ttu-id="11b0a-137">Información sobre la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="11b0a-137">Information about the issuing certificate authority (CA)</span></span>
<span data-ttu-id="11b0a-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="11b0a-138">SignerHash</span></span> | <span data-ttu-id="11b0a-139">string</span><span class="sxs-lookup"><span data-stu-id="11b0a-139">string</span></span> | <span data-ttu-id="11b0a-140">Valor hash único que identifica el firmante</span><span class="sxs-lookup"><span data-stu-id="11b0a-140">Unique hash value identifying the signer</span></span>
<span data-ttu-id="11b0a-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="11b0a-141">IsCertificateValid</span></span> | <span data-ttu-id="11b0a-142">boolean</span><span class="sxs-lookup"><span data-stu-id="11b0a-142">boolean</span></span> | <span data-ttu-id="11b0a-143">Si el certificado usado para firmar el archivo es válido</span><span class="sxs-lookup"><span data-stu-id="11b0a-143">Whether the certificate used to sign the file is valid</span></span>
<span data-ttu-id="11b0a-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="11b0a-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="11b0a-145">boolean</span><span class="sxs-lookup"><span data-stu-id="11b0a-145">boolean</span></span> | <span data-ttu-id="11b0a-146">Indica si el firmante del certificado raíz es Microsoft</span><span class="sxs-lookup"><span data-stu-id="11b0a-146">Indicates whether the signer of the root certificate is Microsoft</span></span>
<span data-ttu-id="11b0a-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="11b0a-147">IsExecutable</span></span> | <span data-ttu-id="11b0a-148">boolean</span><span class="sxs-lookup"><span data-stu-id="11b0a-148">boolean</span></span> | <span data-ttu-id="11b0a-149">Si el archivo es un archivo ejecutable portátil (PE)</span><span class="sxs-lookup"><span data-stu-id="11b0a-149">Whether the file is a Portable Executable (PE) file</span></span>
<span data-ttu-id="11b0a-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="11b0a-150">ThreatName</span></span> | <span data-ttu-id="11b0a-151">string</span><span class="sxs-lookup"><span data-stu-id="11b0a-151">string</span></span> | <span data-ttu-id="11b0a-152">Nombre de detección de cualquier malware u otras amenazas encontradas</span><span class="sxs-lookup"><span data-stu-id="11b0a-152">Detection name for any malware or other threats found</span></span>
<span data-ttu-id="11b0a-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="11b0a-153">Publisher</span></span> | <span data-ttu-id="11b0a-154">string</span><span class="sxs-lookup"><span data-stu-id="11b0a-154">string</span></span> | <span data-ttu-id="11b0a-155">Nombre de la organización que publicó el archivo</span><span class="sxs-lookup"><span data-stu-id="11b0a-155">Name of the organization that published the file</span></span>
<span data-ttu-id="11b0a-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="11b0a-156">SoftwareName</span></span> | <span data-ttu-id="11b0a-157">cadena</span><span class="sxs-lookup"><span data-stu-id="11b0a-157">string</span></span> | <span data-ttu-id="11b0a-158">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="11b0a-158">Name of the software product</span></span>

## <a name="syntax"></a><span data-ttu-id="11b0a-159">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11b0a-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="11b0a-160">Argumentos</span><span class="sxs-lookup"><span data-stu-id="11b0a-160">Arguments</span></span>

- <span data-ttu-id="11b0a-161">**x** : columna de id. de archivo que se `SHA1` usará: `SHA256` , , o ; función usa si no se `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especifica</span><span class="sxs-lookup"><span data-stu-id="11b0a-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="11b0a-162">**y:** límite al número de registros que se enriquecerán, de 1 a 1000; función usa 100 si no se especifica</span><span class="sxs-lookup"><span data-stu-id="11b0a-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="11b0a-163">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="11b0a-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="11b0a-164">Proyecte solo la columna SHA1 y enriquezcala</span><span class="sxs-lookup"><span data-stu-id="11b0a-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="11b0a-165">Enriquecer los primeros 500 registros y enumerar archivos de baja prevalencia</span><span class="sxs-lookup"><span data-stu-id="11b0a-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="11b0a-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="11b0a-166">Related topics</span></span>

- [<span data-ttu-id="11b0a-167">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="11b0a-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="11b0a-168">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="11b0a-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="11b0a-169">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="11b0a-169">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
