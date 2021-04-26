---
title: Tabla DeviceFileCertificateInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la firma de archivos en la tabla DeviceFileCertificateInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, firma digital, certificado, firma de archivos, DeviceFileCertificateInfo
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
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023218"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="0adb6-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="0adb6-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0adb6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0adb6-105">**Applies to:**</span></span>
- <span data-ttu-id="0adb6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0adb6-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="0adb6-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0adb6-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="0adb6-108">La `DeviceFileCertificateInfo` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información acerca de los certificados de firma de archivos.</span><span class="sxs-lookup"><span data-stu-id="0adb6-108">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="0adb6-109">En esta tabla se usan los datos obtenidos de las actividades de verificación de certificados que se realizan regularmente en los archivos de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="0adb6-109">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="0adb6-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0adb6-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0adb6-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="0adb6-111">Column name</span></span> | <span data-ttu-id="0adb6-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0adb6-112">Data type</span></span> | <span data-ttu-id="0adb6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0adb6-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0adb6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="0adb6-114">datetime</span></span> | <span data-ttu-id="0adb6-115">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="0adb6-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0adb6-116">cadena</span><span class="sxs-lookup"><span data-stu-id="0adb6-116">string</span></span> | <span data-ttu-id="0adb6-117">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="0adb6-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0adb6-118">cadena</span><span class="sxs-lookup"><span data-stu-id="0adb6-118">string</span></span> | <span data-ttu-id="0adb6-119">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="0adb6-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="0adb6-120">cadena</span><span class="sxs-lookup"><span data-stu-id="0adb6-120">string</span></span> | <span data-ttu-id="0adb6-121">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="0adb6-121">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="0adb6-122">boolean</span><span class="sxs-lookup"><span data-stu-id="0adb6-122">boolean</span></span> | <span data-ttu-id="0adb6-123">Indica si el archivo está firmado</span><span class="sxs-lookup"><span data-stu-id="0adb6-123">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="0adb6-124">string</span><span class="sxs-lookup"><span data-stu-id="0adb6-124">string</span></span> | <span data-ttu-id="0adb6-125">Indica si la información de firma se leyó como contenido incrustado en el propio archivo o si se leyó desde un archivo de catálogo externo.</span><span class="sxs-lookup"><span data-stu-id="0adb6-125">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="0adb6-126">string</span><span class="sxs-lookup"><span data-stu-id="0adb6-126">string</span></span> | <span data-ttu-id="0adb6-127">Información sobre el firmante del archivo</span><span class="sxs-lookup"><span data-stu-id="0adb6-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="0adb6-128">string</span><span class="sxs-lookup"><span data-stu-id="0adb6-128">string</span></span> | <span data-ttu-id="0adb6-129">Valor hash único que identifica el firmante</span><span class="sxs-lookup"><span data-stu-id="0adb6-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="0adb6-130">string</span><span class="sxs-lookup"><span data-stu-id="0adb6-130">string</span></span> | <span data-ttu-id="0adb6-131">Información sobre la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="0adb6-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="0adb6-132">string</span><span class="sxs-lookup"><span data-stu-id="0adb6-132">string</span></span> | <span data-ttu-id="0adb6-133">Valor hash único que identifica la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="0adb6-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="0adb6-134">string</span><span class="sxs-lookup"><span data-stu-id="0adb6-134">string</span></span> | <span data-ttu-id="0adb6-135">Identificador del certificado que es único para la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="0adb6-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="0adb6-136">string</span><span class="sxs-lookup"><span data-stu-id="0adb6-136">string</span></span> |  <span data-ttu-id="0adb6-137">Matriz JSON que enumera las direcciones URL de recursos compartidos de red que contienen certificados y listas de revocación de certificados (CRL)</span><span class="sxs-lookup"><span data-stu-id="0adb6-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="0adb6-138">datetime</span><span class="sxs-lookup"><span data-stu-id="0adb6-138">datetime</span></span> | <span data-ttu-id="0adb6-139">Fecha y hora en que se creó el certificado</span><span class="sxs-lookup"><span data-stu-id="0adb6-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="0adb6-140">datetime</span><span class="sxs-lookup"><span data-stu-id="0adb6-140">datetime</span></span> | <span data-ttu-id="0adb6-141">Fecha y hora en que el certificado está establecido para expirar</span><span class="sxs-lookup"><span data-stu-id="0adb6-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="0adb6-142">datetime</span><span class="sxs-lookup"><span data-stu-id="0adb6-142">datetime</span></span> | <span data-ttu-id="0adb6-143">Fecha y hora en que se contrasignó el certificado</span><span class="sxs-lookup"><span data-stu-id="0adb6-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="0adb6-144">boolean</span><span class="sxs-lookup"><span data-stu-id="0adb6-144">boolean</span></span> | <span data-ttu-id="0adb6-145">Indica si el archivo es de confianza en función de los resultados de la función WinVerifyTrust, que busca información de certificado raíz desconocido, firmas no válidas, certificados revocados y otros atributos cuestionables</span><span class="sxs-lookup"><span data-stu-id="0adb6-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="0adb6-146">boolean</span><span class="sxs-lookup"><span data-stu-id="0adb6-146">boolean</span></span> | <span data-ttu-id="0adb6-147">Indica si el firmante del certificado raíz es Microsoft</span><span class="sxs-lookup"><span data-stu-id="0adb6-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="0adb6-148">largo</span><span class="sxs-lookup"><span data-stu-id="0adb6-148">long</span></span> | <span data-ttu-id="0adb6-149">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="0adb6-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0adb6-150">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp.</span><span class="sxs-lookup"><span data-stu-id="0adb6-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="0adb6-151">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0adb6-151">Related topics</span></span>
- [<span data-ttu-id="0adb6-152">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="0adb6-152">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0adb6-153">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="0adb6-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0adb6-154">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="0adb6-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0adb6-155">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="0adb6-155">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0adb6-156">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="0adb6-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0adb6-157">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="0adb6-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
