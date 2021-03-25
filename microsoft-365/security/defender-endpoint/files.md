---
title: Tipo de recurso File
description: Recupera alertas recientes de Microsoft Defender para puntos de conexión relacionadas con archivos.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199986"
---
# <a name="file-resource-type"></a><span data-ttu-id="1dcbd-104">Tipo de recurso File</span><span class="sxs-lookup"><span data-stu-id="1dcbd-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1dcbd-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1dcbd-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1dcbd-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="1dcbd-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1dcbd-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1dcbd-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="1dcbd-108">Representa una entidad de archivo en Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="1dcbd-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="1dcbd-109">Methods</span><span class="sxs-lookup"><span data-stu-id="1dcbd-109">Methods</span></span>
<span data-ttu-id="1dcbd-110">Método</span><span class="sxs-lookup"><span data-stu-id="1dcbd-110">Method</span></span>|<span data-ttu-id="1dcbd-111">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1dcbd-111">Return Type</span></span> |<span data-ttu-id="1dcbd-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dcbd-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="1dcbd-113">Obtener archivo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="1dcbd-114">file</span><span class="sxs-lookup"><span data-stu-id="1dcbd-114">file</span></span>](files.md) | <span data-ttu-id="1dcbd-115">Obtener un solo archivo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-115">Get a single file</span></span> 
[<span data-ttu-id="1dcbd-116">Enumerar alertas relacionadas con archivos</span><span class="sxs-lookup"><span data-stu-id="1dcbd-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="1dcbd-117">Colección [alert](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1dcbd-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="1dcbd-118">Obtener las [entidades](alerts.md) de alerta asociadas al archivo.</span><span class="sxs-lookup"><span data-stu-id="1dcbd-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="1dcbd-119">Enumerar máquinas relacionadas con archivos</span><span class="sxs-lookup"><span data-stu-id="1dcbd-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="1dcbd-120">[colección machine](machine.md)</span><span class="sxs-lookup"><span data-stu-id="1dcbd-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="1dcbd-121">Obtener las [entidades](machine.md) del equipo asociadas con la alerta.</span><span class="sxs-lookup"><span data-stu-id="1dcbd-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="1dcbd-122">estadísticas de archivos</span><span class="sxs-lookup"><span data-stu-id="1dcbd-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="1dcbd-123">Resumen de estadísticas</span><span class="sxs-lookup"><span data-stu-id="1dcbd-123">Statistics summary</span></span> | <span data-ttu-id="1dcbd-124">Recupera la prevalencia del archivo determinado.</span><span class="sxs-lookup"><span data-stu-id="1dcbd-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="1dcbd-125">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1dcbd-125">Properties</span></span>
|<span data-ttu-id="1dcbd-126">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1dcbd-126">Property</span></span> | <span data-ttu-id="1dcbd-127">Tipo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-127">Type</span></span>    |   <span data-ttu-id="1dcbd-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dcbd-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="1dcbd-129">sha1</span><span class="sxs-lookup"><span data-stu-id="1dcbd-129">sha1</span></span> | <span data-ttu-id="1dcbd-130">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-130">String</span></span> | <span data-ttu-id="1dcbd-131">Hash Sha1 del contenido del archivo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="1dcbd-132">sha256</span><span class="sxs-lookup"><span data-stu-id="1dcbd-132">sha256</span></span> | <span data-ttu-id="1dcbd-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-133">String</span></span> | <span data-ttu-id="1dcbd-134">Hash Sha256 del contenido del archivo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="1dcbd-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="1dcbd-135">globalPrevalence</span></span> | <span data-ttu-id="1dcbd-136">Long que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="1dcbd-136">Nullable long</span></span> | <span data-ttu-id="1dcbd-137">Prevalencia de archivos en toda la organización</span><span class="sxs-lookup"><span data-stu-id="1dcbd-137">File prevalence across organization</span></span> |
|<span data-ttu-id="1dcbd-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="1dcbd-138">globalFirstObserved</span></span> | <span data-ttu-id="1dcbd-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1dcbd-139">DateTimeOffset</span></span> | <span data-ttu-id="1dcbd-140">Primera vez que se observó el archivo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-140">First time the file was observed</span></span> |
|<span data-ttu-id="1dcbd-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="1dcbd-141">globalLastObserved</span></span> | <span data-ttu-id="1dcbd-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1dcbd-142">DateTimeOffset</span></span> | <span data-ttu-id="1dcbd-143">Última vez que se observó el archivo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-143">Last time the file was observed</span></span> |
|<span data-ttu-id="1dcbd-144">size</span><span class="sxs-lookup"><span data-stu-id="1dcbd-144">size</span></span> | <span data-ttu-id="1dcbd-145">Long que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="1dcbd-145">Nullable long</span></span> | <span data-ttu-id="1dcbd-146">Tamaño del archivo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-146">Size of the file</span></span> |
|<span data-ttu-id="1dcbd-147">fileType</span><span class="sxs-lookup"><span data-stu-id="1dcbd-147">fileType</span></span> | <span data-ttu-id="1dcbd-148">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-148">String</span></span> | <span data-ttu-id="1dcbd-149">Tipo del archivo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-149">Type of the file</span></span> |
|<span data-ttu-id="1dcbd-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="1dcbd-150">isPeFile</span></span> | <span data-ttu-id="1dcbd-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="1dcbd-151">Boolean</span></span> | <span data-ttu-id="1dcbd-152">true si el archivo es ejecutable portátil (por ejemplo, "DLL", "EXE", etc.)</span><span class="sxs-lookup"><span data-stu-id="1dcbd-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="1dcbd-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="1dcbd-153">filePublisher</span></span> | <span data-ttu-id="1dcbd-154">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-154">String</span></span> | <span data-ttu-id="1dcbd-155">Editor de archivos</span><span class="sxs-lookup"><span data-stu-id="1dcbd-155">File publisher</span></span> |
|<span data-ttu-id="1dcbd-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="1dcbd-156">fileProductName</span></span> | <span data-ttu-id="1dcbd-157">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-157">String</span></span> | <span data-ttu-id="1dcbd-158">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1dcbd-158">Product name</span></span> |
|<span data-ttu-id="1dcbd-159">firmante</span><span class="sxs-lookup"><span data-stu-id="1dcbd-159">signer</span></span> | <span data-ttu-id="1dcbd-160">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-160">String</span></span> | <span data-ttu-id="1dcbd-161">Firmante de archivos</span><span class="sxs-lookup"><span data-stu-id="1dcbd-161">File signer</span></span> |
|<span data-ttu-id="1dcbd-162">emisor</span><span class="sxs-lookup"><span data-stu-id="1dcbd-162">issuer</span></span> | <span data-ttu-id="1dcbd-163">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-163">String</span></span> | <span data-ttu-id="1dcbd-164">Emisor de archivos</span><span class="sxs-lookup"><span data-stu-id="1dcbd-164">File issuer</span></span> |
|<span data-ttu-id="1dcbd-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="1dcbd-165">signerHash</span></span> | <span data-ttu-id="1dcbd-166">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-166">String</span></span> | <span data-ttu-id="1dcbd-167">Hash del certificado de firma</span><span class="sxs-lookup"><span data-stu-id="1dcbd-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="1dcbd-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="1dcbd-168">isValidCertificate</span></span> | <span data-ttu-id="1dcbd-169">Booleano</span><span class="sxs-lookup"><span data-stu-id="1dcbd-169">Boolean</span></span> | <span data-ttu-id="1dcbd-170">Se ha comprobado correctamente la firma del certificado por Microsoft Defender para el agente de extremo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="1dcbd-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="1dcbd-171">determinationType</span></span> | <span data-ttu-id="1dcbd-172">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-172">String</span></span> | <span data-ttu-id="1dcbd-173">El tipo de determinación del archivo</span><span class="sxs-lookup"><span data-stu-id="1dcbd-173">The determination type of the file</span></span> |
|<span data-ttu-id="1dcbd-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="1dcbd-174">determinationValue</span></span> | <span data-ttu-id="1dcbd-175">Cadena</span><span class="sxs-lookup"><span data-stu-id="1dcbd-175">String</span></span> | <span data-ttu-id="1dcbd-176">Valor de determinación</span><span class="sxs-lookup"><span data-stu-id="1dcbd-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="1dcbd-177">Representación json</span><span class="sxs-lookup"><span data-stu-id="1dcbd-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
