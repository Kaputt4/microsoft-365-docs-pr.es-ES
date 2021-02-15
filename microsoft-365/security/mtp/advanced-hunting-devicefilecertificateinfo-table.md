---
title: Tabla DeviceFileCertificateInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la firma de archivos en la tabla DeviceFileCertificateInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, firma digital, certificado, firma de archivos, DeviceFileCertificateInfo
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
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931319"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="7d277-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="7d277-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7d277-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7d277-105">**Applies to:**</span></span>
- <span data-ttu-id="7d277-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d277-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7d277-107">La `DeviceFileCertificateInfo` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre los certificados de firma de archivos.</span><span class="sxs-lookup"><span data-stu-id="7d277-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="7d277-108">En esta tabla se usan los datos obtenidos de las actividades de comprobación de certificados que se realizan periódicamente en los archivos de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="7d277-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="7d277-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7d277-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7d277-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="7d277-110">Column name</span></span> | <span data-ttu-id="7d277-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7d277-111">Data type</span></span> | <span data-ttu-id="7d277-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d277-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7d277-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7d277-113">datetime</span></span> | <span data-ttu-id="7d277-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="7d277-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="7d277-115">cadena</span><span class="sxs-lookup"><span data-stu-id="7d277-115">string</span></span> | <span data-ttu-id="7d277-116">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="7d277-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7d277-117">cadena</span><span class="sxs-lookup"><span data-stu-id="7d277-117">string</span></span> | <span data-ttu-id="7d277-118">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="7d277-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="7d277-119">cadena</span><span class="sxs-lookup"><span data-stu-id="7d277-119">string</span></span> | <span data-ttu-id="7d277-120">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="7d277-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="7d277-121">boolean</span><span class="sxs-lookup"><span data-stu-id="7d277-121">boolean</span></span> | <span data-ttu-id="7d277-122">Indica si el archivo está firmado</span><span class="sxs-lookup"><span data-stu-id="7d277-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="7d277-123">string</span><span class="sxs-lookup"><span data-stu-id="7d277-123">string</span></span> | <span data-ttu-id="7d277-124">Indica si la información de firma se leyó como contenido incrustado en el propio archivo o se leyó desde un archivo de catálogo externo.</span><span class="sxs-lookup"><span data-stu-id="7d277-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="7d277-125">string</span><span class="sxs-lookup"><span data-stu-id="7d277-125">string</span></span> | <span data-ttu-id="7d277-126">Información sobre el firmante del archivo</span><span class="sxs-lookup"><span data-stu-id="7d277-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="7d277-127">string</span><span class="sxs-lookup"><span data-stu-id="7d277-127">string</span></span> | <span data-ttu-id="7d277-128">Valor hash único que identifica al firmante</span><span class="sxs-lookup"><span data-stu-id="7d277-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="7d277-129">string</span><span class="sxs-lookup"><span data-stu-id="7d277-129">string</span></span> | <span data-ttu-id="7d277-130">Información sobre la entidad de certificación (CA) emisora</span><span class="sxs-lookup"><span data-stu-id="7d277-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="7d277-131">string</span><span class="sxs-lookup"><span data-stu-id="7d277-131">string</span></span> | <span data-ttu-id="7d277-132">Valor hash único que identifica la entidad de certificación (CA) emisora</span><span class="sxs-lookup"><span data-stu-id="7d277-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="7d277-133">string</span><span class="sxs-lookup"><span data-stu-id="7d277-133">string</span></span> | <span data-ttu-id="7d277-134">Identificador del certificado que es único para la entidad de certificación (CA) emisora</span><span class="sxs-lookup"><span data-stu-id="7d277-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="7d277-135">string</span><span class="sxs-lookup"><span data-stu-id="7d277-135">string</span></span> |  <span data-ttu-id="7d277-136">Matriz JSON que enumera las direcciones URL de recursos compartidos de red que contienen certificados y listas de revocación de certificados (CRL)</span><span class="sxs-lookup"><span data-stu-id="7d277-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="7d277-137">datetime</span><span class="sxs-lookup"><span data-stu-id="7d277-137">datetime</span></span> | <span data-ttu-id="7d277-138">Fecha y hora en que se creó el certificado</span><span class="sxs-lookup"><span data-stu-id="7d277-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="7d277-139">datetime</span><span class="sxs-lookup"><span data-stu-id="7d277-139">datetime</span></span> | <span data-ttu-id="7d277-140">Fecha y hora en que el certificado está configurado para expirar</span><span class="sxs-lookup"><span data-stu-id="7d277-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="7d277-141">datetime</span><span class="sxs-lookup"><span data-stu-id="7d277-141">datetime</span></span> | <span data-ttu-id="7d277-142">Fecha y hora en que se contrafirmó el certificado</span><span class="sxs-lookup"><span data-stu-id="7d277-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="7d277-143">boolean</span><span class="sxs-lookup"><span data-stu-id="7d277-143">boolean</span></span> | <span data-ttu-id="7d277-144">Indica si el archivo es de confianza en función de los resultados de la función WinVerifyTrust, que comprueba si hay información de certificado raíz desconocida, firmas no válidas, certificados revocados y otros atributos que pueden ser cuestionables.</span><span class="sxs-lookup"><span data-stu-id="7d277-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="7d277-145">boolean</span><span class="sxs-lookup"><span data-stu-id="7d277-145">boolean</span></span> | <span data-ttu-id="7d277-146">Indica si el firmante del certificado raíz es Microsoft</span><span class="sxs-lookup"><span data-stu-id="7d277-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="7d277-147">largo</span><span class="sxs-lookup"><span data-stu-id="7d277-147">long</span></span> | <span data-ttu-id="7d277-148">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="7d277-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="7d277-149">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp.</span><span class="sxs-lookup"><span data-stu-id="7d277-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="7d277-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7d277-150">Related topics</span></span>
- [<span data-ttu-id="7d277-151">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="7d277-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7d277-152">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="7d277-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7d277-153">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="7d277-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7d277-154">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="7d277-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7d277-155">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="7d277-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7d277-156">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="7d277-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
