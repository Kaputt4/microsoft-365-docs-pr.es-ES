---
title: Tabla DeviceFileCertificateInfoBeta en el esquema de búsqueda avanzada
description: Información sobre la firma de archivos en la tabla DeviceFileCertificateInfoBeta del esquema de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, firma digital, certificado, firma de archivos DeviceFileCertificateInfoBeta
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
ms.openlocfilehash: ffff2802b52fb48bd7fc88fc0d3eac425380502e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602839"
---
# <a name="devicefilecertificateinfobeta"></a><span data-ttu-id="693c7-104">DeviceFileCertificateInfoBeta</span><span class="sxs-lookup"><span data-stu-id="693c7-104">DeviceFileCertificateInfoBeta</span></span>

<span data-ttu-id="693c7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="693c7-105">**Applies to:**</span></span>
- <span data-ttu-id="693c7-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="693c7-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="693c7-107">La `DeviceFileCertificateInfoBeta` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los certificados de firma de archivos.</span><span class="sxs-lookup"><span data-stu-id="693c7-107">The `DeviceFileCertificateInfoBeta` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="693c7-108">En esta tabla se usan los datos obtenidos de las actividades de comprobación de certificados realizadas regularmente en los archivos de los extremos.</span><span class="sxs-lookup"><span data-stu-id="693c7-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="693c7-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="693c7-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="693c7-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="693c7-110">Column name</span></span> | <span data-ttu-id="693c7-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="693c7-111">Data type</span></span> | <span data-ttu-id="693c7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="693c7-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="693c7-113">datetime</span><span class="sxs-lookup"><span data-stu-id="693c7-113">datetime</span></span> | <span data-ttu-id="693c7-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="693c7-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="693c7-115">string</span><span class="sxs-lookup"><span data-stu-id="693c7-115">string</span></span> | <span data-ttu-id="693c7-116">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="693c7-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="693c7-117">string</span><span class="sxs-lookup"><span data-stu-id="693c7-117">string</span></span> | <span data-ttu-id="693c7-118">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="693c7-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="693c7-119">cadena</span><span class="sxs-lookup"><span data-stu-id="693c7-119">string</span></span> | <span data-ttu-id="693c7-120">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="693c7-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="693c7-121">boolean</span><span class="sxs-lookup"><span data-stu-id="693c7-121">boolean</span></span> | <span data-ttu-id="693c7-122">Indica si el archivo está firmado</span><span class="sxs-lookup"><span data-stu-id="693c7-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="693c7-123">string</span><span class="sxs-lookup"><span data-stu-id="693c7-123">string</span></span> | <span data-ttu-id="693c7-124">Indica si la información de firma se leyó como contenido insertado en el propio archivo o se lee en un archivo de catálogo externo</span><span class="sxs-lookup"><span data-stu-id="693c7-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="693c7-125">string</span><span class="sxs-lookup"><span data-stu-id="693c7-125">string</span></span> | <span data-ttu-id="693c7-126">Información sobre el firmante del archivo</span><span class="sxs-lookup"><span data-stu-id="693c7-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="693c7-127">string</span><span class="sxs-lookup"><span data-stu-id="693c7-127">string</span></span> | <span data-ttu-id="693c7-128">Valor hash único que identifica al firmante</span><span class="sxs-lookup"><span data-stu-id="693c7-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="693c7-129">string</span><span class="sxs-lookup"><span data-stu-id="693c7-129">string</span></span> | <span data-ttu-id="693c7-130">Información sobre la entidad de certificación (CA) emisora</span><span class="sxs-lookup"><span data-stu-id="693c7-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="693c7-131">string</span><span class="sxs-lookup"><span data-stu-id="693c7-131">string</span></span> | <span data-ttu-id="693c7-132">Valor hash único que identifica a la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="693c7-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="693c7-133">string</span><span class="sxs-lookup"><span data-stu-id="693c7-133">string</span></span> | <span data-ttu-id="693c7-134">Identificador del certificado que es único para la entidad de certificación (CA) emisora</span><span class="sxs-lookup"><span data-stu-id="693c7-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="693c7-135">string</span><span class="sxs-lookup"><span data-stu-id="693c7-135">string</span></span> |  <span data-ttu-id="693c7-136">Matriz JSON donde se muestran las direcciones URL de los recursos compartidos de red que contienen certificados y listas de revocación de certificados (CRL)</span><span class="sxs-lookup"><span data-stu-id="693c7-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="693c7-137">datetime</span><span class="sxs-lookup"><span data-stu-id="693c7-137">datetime</span></span> | <span data-ttu-id="693c7-138">Fecha y hora de creación del certificado</span><span class="sxs-lookup"><span data-stu-id="693c7-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="693c7-139">datetime</span><span class="sxs-lookup"><span data-stu-id="693c7-139">datetime</span></span> | <span data-ttu-id="693c7-140">Fecha y hora en que el certificado está configurado para expirar</span><span class="sxs-lookup"><span data-stu-id="693c7-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="693c7-141">datetime</span><span class="sxs-lookup"><span data-stu-id="693c7-141">datetime</span></span> | <span data-ttu-id="693c7-142">Fecha y hora en que se contrasignó el certificado</span><span class="sxs-lookup"><span data-stu-id="693c7-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="693c7-143">boolean</span><span class="sxs-lookup"><span data-stu-id="693c7-143">boolean</span></span> | <span data-ttu-id="693c7-144">Indica si el archivo es de confianza en función de los resultados de la función WinVerifyTrust, que comprueba si hay información de certificado raíz desconocida, firmas no válidas, certificados revocados y otros atributos cuestionables</span><span class="sxs-lookup"><span data-stu-id="693c7-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="693c7-145">boolean</span><span class="sxs-lookup"><span data-stu-id="693c7-145">boolean</span></span> | <span data-ttu-id="693c7-146">Indica si el firmante del certificado raíz es Microsoft</span><span class="sxs-lookup"><span data-stu-id="693c7-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="693c7-147">largo</span><span class="sxs-lookup"><span data-stu-id="693c7-147">long</span></span> | <span data-ttu-id="693c7-148">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="693c7-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="693c7-149">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp.</span><span class="sxs-lookup"><span data-stu-id="693c7-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="693c7-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="693c7-150">Related topics</span></span>
- [<span data-ttu-id="693c7-151">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="693c7-151">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="693c7-152">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="693c7-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="693c7-153">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="693c7-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="693c7-154">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="693c7-154">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="693c7-155">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="693c7-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="693c7-156">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="693c7-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)