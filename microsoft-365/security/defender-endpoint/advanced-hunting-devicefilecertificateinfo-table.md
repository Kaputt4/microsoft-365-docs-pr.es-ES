---
title: Tabla DeviceFileCertificateInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la firma de archivos en la tabla DeviceFileCertificateInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, firma digital, certificado, firma de archivos, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499178"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="c48e5-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="c48e5-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c48e5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c48e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="c48e5-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c48e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="c48e5-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c48e5-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c48e5-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c48e5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="c48e5-109">La `DeviceFileCertificateInfo` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información acerca de los certificados de firma de archivos.</span><span class="sxs-lookup"><span data-stu-id="c48e5-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="c48e5-110">En esta tabla se usan los datos obtenidos de las actividades de verificación de certificados que se realizan regularmente en los archivos de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="c48e5-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="c48e5-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c48e5-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="c48e5-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="c48e5-112">Column name</span></span> | <span data-ttu-id="c48e5-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c48e5-113">Data type</span></span> | <span data-ttu-id="c48e5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c48e5-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c48e5-115">datetime</span><span class="sxs-lookup"><span data-stu-id="c48e5-115">datetime</span></span> | <span data-ttu-id="c48e5-116">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="c48e5-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c48e5-117">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-117">string</span></span> | <span data-ttu-id="c48e5-118">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="c48e5-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c48e5-119">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-119">string</span></span> | <span data-ttu-id="c48e5-120">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c48e5-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="c48e5-121">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-121">string</span></span> | <span data-ttu-id="c48e5-122">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="c48e5-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="c48e5-123">boolean</span><span class="sxs-lookup"><span data-stu-id="c48e5-123">boolean</span></span> | <span data-ttu-id="c48e5-124">Indica si el archivo está firmado</span><span class="sxs-lookup"><span data-stu-id="c48e5-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="c48e5-125">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-125">string</span></span> | <span data-ttu-id="c48e5-126">Indica si la información de firma se leyó como contenido incrustado en el propio archivo o si se leyó desde un archivo de catálogo externo.</span><span class="sxs-lookup"><span data-stu-id="c48e5-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="c48e5-127">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-127">string</span></span> | <span data-ttu-id="c48e5-128">Información sobre el firmante del archivo</span><span class="sxs-lookup"><span data-stu-id="c48e5-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="c48e5-129">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-129">string</span></span> | <span data-ttu-id="c48e5-130">Valor hash único que identifica el firmante</span><span class="sxs-lookup"><span data-stu-id="c48e5-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="c48e5-131">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-131">string</span></span> | <span data-ttu-id="c48e5-132">Información sobre la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="c48e5-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="c48e5-133">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-133">string</span></span> | <span data-ttu-id="c48e5-134">Valor hash único que identifica la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="c48e5-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="c48e5-135">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-135">string</span></span> | <span data-ttu-id="c48e5-136">Identificador del certificado que es único para la entidad emisora de certificados (CA)</span><span class="sxs-lookup"><span data-stu-id="c48e5-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="c48e5-137">cadena</span><span class="sxs-lookup"><span data-stu-id="c48e5-137">string</span></span> |  <span data-ttu-id="c48e5-138">Matriz JSON que enumera las direcciones URL de recursos compartidos de red que contienen certificados y listas de revocación de certificados (CRL)</span><span class="sxs-lookup"><span data-stu-id="c48e5-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="c48e5-139">datetime</span><span class="sxs-lookup"><span data-stu-id="c48e5-139">datetime</span></span> | <span data-ttu-id="c48e5-140">Fecha y hora en que se creó el certificado</span><span class="sxs-lookup"><span data-stu-id="c48e5-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="c48e5-141">datetime</span><span class="sxs-lookup"><span data-stu-id="c48e5-141">datetime</span></span> | <span data-ttu-id="c48e5-142">Fecha y hora en que el certificado está establecido para expirar</span><span class="sxs-lookup"><span data-stu-id="c48e5-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="c48e5-143">datetime</span><span class="sxs-lookup"><span data-stu-id="c48e5-143">datetime</span></span> | <span data-ttu-id="c48e5-144">Fecha y hora en que se contrasignó el certificado</span><span class="sxs-lookup"><span data-stu-id="c48e5-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="c48e5-145">boolean</span><span class="sxs-lookup"><span data-stu-id="c48e5-145">boolean</span></span> | <span data-ttu-id="c48e5-146">Indica si el archivo es de confianza en función de los resultados de la función WinVerifyTrust, que busca información de certificado raíz desconocido, firmas no válidas, certificados revocados y otros atributos cuestionables</span><span class="sxs-lookup"><span data-stu-id="c48e5-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="c48e5-147">boolean</span><span class="sxs-lookup"><span data-stu-id="c48e5-147">boolean</span></span> | <span data-ttu-id="c48e5-148">Indica si el firmante del certificado raíz es Microsoft</span><span class="sxs-lookup"><span data-stu-id="c48e5-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="c48e5-149">largo</span><span class="sxs-lookup"><span data-stu-id="c48e5-149">long</span></span> | <span data-ttu-id="c48e5-150">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="c48e5-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c48e5-151">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp.</span><span class="sxs-lookup"><span data-stu-id="c48e5-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="c48e5-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c48e5-152">Related topics</span></span>
- [<span data-ttu-id="c48e5-153">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="c48e5-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c48e5-154">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="c48e5-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c48e5-155">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="c48e5-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
