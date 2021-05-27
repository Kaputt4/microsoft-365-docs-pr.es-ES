---
title: Evaluación de vulnerabilidades de software de exportación por dispositivo
description: La respuesta de la API es por dispositivo y contiene software vulnerable instalado en los dispositivos expuestos, así como cualquier vulnerabilidad conocida en estos productos de software. Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad.
keywords: api, apis, evaluación de exportación, evaluación por dispositivo, informe de evaluación de vulnerabilidad, evaluación de vulnerabilidad de dispositivo, informe de vulnerabilidad de dispositivo, evaluación de configuración segura, informe de configuración segura, evaluación de vulnerabilidades de software, informe de vulnerabilidades de software, informe de vulnerabilidad por máquina,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689218"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="f46aa-105">Evaluación de vulnerabilidades de software de exportación por dispositivo</span><span class="sxs-lookup"><span data-stu-id="f46aa-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f46aa-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f46aa-106">**Applies to:**</span></span>

- [<span data-ttu-id="f46aa-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f46aa-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f46aa-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f46aa-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f46aa-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f46aa-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f46aa-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f46aa-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="f46aa-111">Devuelve todas las vulnerabilidades de software conocidas y sus detalles para todos los dispositivos, por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f46aa-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="f46aa-112">Hay diferentes llamadas API para obtener diferentes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="f46aa-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="f46aa-113">Dado que la cantidad de datos puede ser muy grande, hay dos formas de recuperarlos:</span><span class="sxs-lookup"><span data-stu-id="f46aa-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="f46aa-114">[Evaluación de vulnerabilidades de software de exportación de OData](#1-export-software-vulnerabilities-assessment-odata)  La API extrae todos los datos de la organización como respuestas Json, siguiendo el protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="f46aa-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="f46aa-115">Este método es el mejor para _organizaciones pequeñas con dispositivos de menos de 100 K._</span><span class="sxs-lookup"><span data-stu-id="f46aa-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="f46aa-116">La respuesta se pagina, por lo que puede usar el campo odata.nextLink de la respuesta \@ para obtener los siguientes resultados.</span><span class="sxs-lookup"><span data-stu-id="f46aa-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="f46aa-117">[Evaluación de vulnerabilidades de software de exportación a través de archivos](#2-export-software-vulnerabilities-assessment-via-files) Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable.</span><span class="sxs-lookup"><span data-stu-id="f46aa-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="f46aa-118">Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f46aa-118">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="f46aa-119">Esta API extrae todos los datos de la organización como archivos de descarga.</span><span class="sxs-lookup"><span data-stu-id="f46aa-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="f46aa-120">La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="f46aa-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="f46aa-121">Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f46aa-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="f46aa-122">Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="f46aa-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="f46aa-123">Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.</span><span class="sxs-lookup"><span data-stu-id="f46aa-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="f46aa-124">Los datos recopilados (mediante _OData_ o a través de _archivos)_ son la instantánea actual del estado actual y no contienen datos históricos.</span><span class="sxs-lookup"><span data-stu-id="f46aa-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="f46aa-125">Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.</span><span class="sxs-lookup"><span data-stu-id="f46aa-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="f46aa-126">A menos que se indique lo \*\*\*\* contrario, todos los métodos de evaluación de exportación enumerados son exportación completa y por **_dispositivo_** (también **_denominados por dispositivo_**).</span><span class="sxs-lookup"><span data-stu-id="f46aa-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="f46aa-127">1. Evaluación de vulnerabilidades de software de exportación (OData)</span><span class="sxs-lookup"><span data-stu-id="f46aa-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="f46aa-128">Descripción del método de api 1.1</span><span class="sxs-lookup"><span data-stu-id="f46aa-128">1.1 API method description</span></span>

<span data-ttu-id="f46aa-129">Esta respuesta de la API contiene todos los datos del software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f46aa-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="f46aa-130">Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="f46aa-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="f46aa-131">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="f46aa-131">Limitations</span></span>

>- <span data-ttu-id="f46aa-132">El tamaño máximo de página es 200 000.</span><span class="sxs-lookup"><span data-stu-id="f46aa-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="f46aa-133">Las limitaciones de velocidad para esta API son 30 llamadas por minuto y 1000 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="f46aa-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="f46aa-134">1.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="f46aa-134">1.2 Permissions</span></span>

<span data-ttu-id="f46aa-135">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="f46aa-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f46aa-136">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f46aa-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="f46aa-137">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="f46aa-137">Permission type</span></span> | <span data-ttu-id="f46aa-138">Permiso</span><span class="sxs-lookup"><span data-stu-id="f46aa-138">Permission</span></span> | <span data-ttu-id="f46aa-139">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="f46aa-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="f46aa-140">Aplicación</span><span class="sxs-lookup"><span data-stu-id="f46aa-140">Application</span></span> | <span data-ttu-id="f46aa-141">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="f46aa-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="f46aa-142">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="f46aa-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="f46aa-143">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="f46aa-143">Delegated (work or school account)</span></span> | <span data-ttu-id="f46aa-144">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="f46aa-144">Vulnerability.Read</span></span> | <span data-ttu-id="f46aa-145">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="f46aa-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="f46aa-146">DIRECCIÓN URL 1.3</span><span class="sxs-lookup"><span data-stu-id="f46aa-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="f46aa-147">1.4 Parámetros</span><span class="sxs-lookup"><span data-stu-id="f46aa-147">1.4 Parameters</span></span>

- <span data-ttu-id="f46aa-148">pageSize (valor predeterminado = 50.000): número de resultados en la respuesta</span><span class="sxs-lookup"><span data-stu-id="f46aa-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="f46aa-149">$top: número de resultados que se devolverán (no devuelve @odata.nextLink y, por lo tanto, no extrae todos los datos)</span><span class="sxs-lookup"><span data-stu-id="f46aa-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="f46aa-150">1.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="f46aa-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="f46aa-151">Cada registro tiene aproximadamente 1 KB de datos.</span><span class="sxs-lookup"><span data-stu-id="f46aa-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="f46aa-152">Debe tener esto en cuenta al elegir el parámetro pageSize correcto.</span><span class="sxs-lookup"><span data-stu-id="f46aa-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="f46aa-153">Es posible que se devuelvan algunas columnas adicionales en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f46aa-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="f46aa-154">Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.</span><span class="sxs-lookup"><span data-stu-id="f46aa-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="f46aa-155">Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f46aa-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="f46aa-156">Al ejecutar esta API, el resultado resultante no se devolverá necesariamente en el mismo orden enumerado en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="f46aa-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="f46aa-157">Propiedad (ID)</span><span class="sxs-lookup"><span data-stu-id="f46aa-157">Property (ID)</span></span> | <span data-ttu-id="f46aa-158">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f46aa-158">Data type</span></span> | <span data-ttu-id="f46aa-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="f46aa-159">Description</span></span> | <span data-ttu-id="f46aa-160">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f46aa-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f46aa-161">CveId</span><span class="sxs-lookup"><span data-stu-id="f46aa-161">CveId</span></span> | <span data-ttu-id="f46aa-162">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-162">string</span></span> | <span data-ttu-id="f46aa-163">Identificador único asignado a la vulnerabilidad de seguridad en el sistema vulnerabilidades y exposiciones comunes (CVE).</span><span class="sxs-lookup"><span data-stu-id="f46aa-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="f46aa-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="f46aa-164">CVE-2020-15992</span></span>
<span data-ttu-id="f46aa-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="f46aa-165">CvssScore</span></span> | <span data-ttu-id="f46aa-166">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-166">string</span></span> | <span data-ttu-id="f46aa-167">La puntuación CVSS de CVE.</span><span class="sxs-lookup"><span data-stu-id="f46aa-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="f46aa-168">6.2</span><span class="sxs-lookup"><span data-stu-id="f46aa-168">6.2</span></span>
<span data-ttu-id="f46aa-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="f46aa-169">DeviceId</span></span> | <span data-ttu-id="f46aa-170">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-170">string</span></span> | <span data-ttu-id="f46aa-171">Identificador único del dispositivo en el servicio.</span><span class="sxs-lookup"><span data-stu-id="f46aa-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="f46aa-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="f46aa-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="f46aa-173">DeviceName</span><span class="sxs-lookup"><span data-stu-id="f46aa-173">DeviceName</span></span> | <span data-ttu-id="f46aa-174">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-174">string</span></span> | <span data-ttu-id="f46aa-175">Nombre de dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f46aa-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="f46aa-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f46aa-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="f46aa-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="f46aa-177">DiskPaths</span></span>  | <span data-ttu-id="f46aa-178">Cadena de \[ matriz\]</span><span class="sxs-lookup"><span data-stu-id="f46aa-178">Array\[string\]</span></span> | <span data-ttu-id="f46aa-179">Prueba en disco de que el producto está instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f46aa-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="f46aa-180">[ "C:\Archivos de programa (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="f46aa-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="f46aa-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="f46aa-181">ExploitabilityLevel</span></span> | <span data-ttu-id="f46aa-182">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-182">string</span></span> | <span data-ttu-id="f46aa-183">El nivel de vulnerabilidad de esta vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="f46aa-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="f46aa-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="f46aa-184">ExploitIsInKit</span></span>
<span data-ttu-id="f46aa-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="f46aa-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="f46aa-186">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-186">string</span></span> | <span data-ttu-id="f46aa-187">Primera vez que se vio la CVE de este producto en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f46aa-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="f46aa-188">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="f46aa-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="f46aa-189">Id</span><span class="sxs-lookup"><span data-stu-id="f46aa-189">Id</span></span> | <span data-ttu-id="f46aa-190">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-190">string</span></span> | <span data-ttu-id="f46aa-191">Identificador único del registro.</span><span class="sxs-lookup"><span data-stu-id="f46aa-191">Unique identifier for the record.</span></span> | <span data-ttu-id="f46aa-192">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="f46aa-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="f46aa-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="f46aa-193">LastSeenTimestamp</span></span> | <span data-ttu-id="f46aa-194">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-194">string</span></span> | <span data-ttu-id="f46aa-195">La última vez que se vio CVE en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f46aa-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="f46aa-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="f46aa-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="f46aa-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="f46aa-197">OSPlatform</span></span> | <span data-ttu-id="f46aa-198">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-198">string</span></span> | <span data-ttu-id="f46aa-199">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f46aa-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f46aa-200">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f46aa-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="f46aa-201">Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f46aa-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="f46aa-202">Windows10</span><span class="sxs-lookup"><span data-stu-id="f46aa-202">Windows10</span></span>
<span data-ttu-id="f46aa-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="f46aa-203">RbacGroupName</span></span>  | <span data-ttu-id="f46aa-204">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-204">string</span></span> | <span data-ttu-id="f46aa-205">Grupo de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="f46aa-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="f46aa-206">Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="f46aa-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="f46aa-207">Si la organización no contiene ningún grupo RBAC, el valor será "None".</span><span class="sxs-lookup"><span data-stu-id="f46aa-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="f46aa-208">Servidores</span><span class="sxs-lookup"><span data-stu-id="f46aa-208">Servers</span></span>
<span data-ttu-id="f46aa-209">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="f46aa-209">RecommendationReference</span></span> | <span data-ttu-id="f46aa-210">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-210">string</span></span> | <span data-ttu-id="f46aa-211">Una referencia al identificador de recomendación relacionado con este software.</span><span class="sxs-lookup"><span data-stu-id="f46aa-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="f46aa-212">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="f46aa-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="f46aa-213">RecommendedSecurityUpdate (opcional)</span><span class="sxs-lookup"><span data-stu-id="f46aa-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="f46aa-214">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-214">string</span></span> | <span data-ttu-id="f46aa-215">Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="f46aa-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="f46aa-216">Actualizaciones de seguridad de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="f46aa-216">April 2020 Security Updates</span></span>
<span data-ttu-id="f46aa-217">RecommendedSecurityUpdateId (opcional)</span><span class="sxs-lookup"><span data-stu-id="f46aa-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="f46aa-218">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-218">string</span></span> | <span data-ttu-id="f46aa-219">Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes</span><span class="sxs-lookup"><span data-stu-id="f46aa-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="f46aa-220">4550961</span><span class="sxs-lookup"><span data-stu-id="f46aa-220">4550961</span></span>
<span data-ttu-id="f46aa-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="f46aa-221">RegistryPaths</span></span>  | <span data-ttu-id="f46aa-222">Cadena de \[ matriz\]</span><span class="sxs-lookup"><span data-stu-id="f46aa-222">Array\[string\]</span></span> | <span data-ttu-id="f46aa-223">El Registro evidencia que el producto está instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f46aa-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="f46aa-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="f46aa-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="f46aa-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="f46aa-225">SoftwareName</span></span> | <span data-ttu-id="f46aa-226">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-226">string</span></span> | <span data-ttu-id="f46aa-227">Nombre del producto de software.</span><span class="sxs-lookup"><span data-stu-id="f46aa-227">Name of the software product.</span></span> | <span data-ttu-id="f46aa-228">chrome</span><span class="sxs-lookup"><span data-stu-id="f46aa-228">chrome</span></span>
<span data-ttu-id="f46aa-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="f46aa-229">SoftwareVendor</span></span> | <span data-ttu-id="f46aa-230">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-230">string</span></span> | <span data-ttu-id="f46aa-231">Nombre del proveedor de software.</span><span class="sxs-lookup"><span data-stu-id="f46aa-231">Name of the software vendor.</span></span> | <span data-ttu-id="f46aa-232">google</span><span class="sxs-lookup"><span data-stu-id="f46aa-232">google</span></span>
<span data-ttu-id="f46aa-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="f46aa-233">SoftwareVersion</span></span> | <span data-ttu-id="f46aa-234">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-234">string</span></span> | <span data-ttu-id="f46aa-235">Número de versión del producto de software.</span><span class="sxs-lookup"><span data-stu-id="f46aa-235">Version number of the software product.</span></span> | <span data-ttu-id="f46aa-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="f46aa-236">81.0.4044.138</span></span>
<span data-ttu-id="f46aa-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="f46aa-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="f46aa-238">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-238">string</span></span> | <span data-ttu-id="f46aa-239">Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS y los factores dinámicos influenciados por el panorama de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f46aa-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="f46aa-240">Medio</span><span class="sxs-lookup"><span data-stu-id="f46aa-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="f46aa-241">1.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f46aa-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="f46aa-242">1.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="f46aa-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="f46aa-243">Ejemplo de respuesta 1.6.2</span><span class="sxs-lookup"><span data-stu-id="f46aa-243">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="f46aa-244">2. Evaluación de vulnerabilidades de software de exportación (a través de archivos)</span><span class="sxs-lookup"><span data-stu-id="f46aa-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="f46aa-245">Descripción del método api 2.1</span><span class="sxs-lookup"><span data-stu-id="f46aa-245">2.1 API method description</span></span>

<span data-ttu-id="f46aa-246">Esta respuesta de la API contiene todos los datos del software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f46aa-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="f46aa-247">Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="f46aa-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="f46aa-248">2.1.2 Limitaciones</span><span class="sxs-lookup"><span data-stu-id="f46aa-248">2.1.2 Limitations</span></span>

<span data-ttu-id="f46aa-249">Las limitaciones de velocidad para esta API son 5 llamadas por minuto y 20 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="f46aa-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="f46aa-250">2.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="f46aa-250">2.2 Permissions</span></span>

<span data-ttu-id="f46aa-251">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="f46aa-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f46aa-252">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f46aa-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="f46aa-253">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="f46aa-253">Permission type</span></span> | <span data-ttu-id="f46aa-254">Permiso</span><span class="sxs-lookup"><span data-stu-id="f46aa-254">Permission</span></span> | <span data-ttu-id="f46aa-255">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="f46aa-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="f46aa-256">Aplicación</span><span class="sxs-lookup"><span data-stu-id="f46aa-256">Application</span></span> | <span data-ttu-id="f46aa-257">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="f46aa-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="f46aa-258">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="f46aa-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="f46aa-259">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="f46aa-259">Delegated (work or school account)</span></span> | <span data-ttu-id="f46aa-260">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="f46aa-260">Vulnerability.Read</span></span> | <span data-ttu-id="f46aa-261">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="f46aa-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="f46aa-262">DIRECCIÓN URL 2.3</span><span class="sxs-lookup"><span data-stu-id="f46aa-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="f46aa-263">Parámetros 2.4</span><span class="sxs-lookup"><span data-stu-id="f46aa-263">2.4 Parameters</span></span>

- <span data-ttu-id="f46aa-264">sasValidHours: el número de horas durante las que las direcciones URL de descarga serán válidas (máximo 24 horas)</span><span class="sxs-lookup"><span data-stu-id="f46aa-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="f46aa-265">2.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="f46aa-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="f46aa-266">Los archivos son archivos comprimidos de gzip & en formato Json de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="f46aa-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="f46aa-267">Las direcciones URL de descarga solo son válidas durante 3 horas; de lo contrario, puede usar el parámetro.</span><span class="sxs-lookup"><span data-stu-id="f46aa-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="f46aa-268">Para obtener la velocidad máxima de descarga de los datos, puede asegurarse de que está descargando desde la misma región de Azure en la que residen los datos.</span><span class="sxs-lookup"><span data-stu-id="f46aa-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="f46aa-269">Cada registro tiene aproximadamente 1 KB de datos.</span><span class="sxs-lookup"><span data-stu-id="f46aa-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="f46aa-270">Debe tener esto en cuenta al elegir el parámetro pageSize correcto.</span><span class="sxs-lookup"><span data-stu-id="f46aa-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="f46aa-271">Es posible que se devuelvan algunas columnas adicionales en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f46aa-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="f46aa-272">Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.</span><span class="sxs-lookup"><span data-stu-id="f46aa-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="f46aa-273">Propiedad (ID)</span><span class="sxs-lookup"><span data-stu-id="f46aa-273">Property (ID)</span></span> | <span data-ttu-id="f46aa-274">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f46aa-274">Data type</span></span> | <span data-ttu-id="f46aa-275">Descripción</span><span class="sxs-lookup"><span data-stu-id="f46aa-275">Description</span></span> | <span data-ttu-id="f46aa-276">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f46aa-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f46aa-277">Exportar archivos</span><span class="sxs-lookup"><span data-stu-id="f46aa-277">Export files</span></span> | <span data-ttu-id="f46aa-278">cadena de \[ matriz\]</span><span class="sxs-lookup"><span data-stu-id="f46aa-278">array\[string\]</span></span>  | <span data-ttu-id="f46aa-279">Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización.</span><span class="sxs-lookup"><span data-stu-id="f46aa-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="f46aa-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="f46aa-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="f46aa-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="f46aa-281">GeneratedTime</span></span> | <span data-ttu-id="f46aa-282">string</span><span class="sxs-lookup"><span data-stu-id="f46aa-282">string</span></span> | <span data-ttu-id="f46aa-283">Hora en que se generó la exportación.</span><span class="sxs-lookup"><span data-stu-id="f46aa-283">The time that the export was generated.</span></span> | <span data-ttu-id="f46aa-284">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="f46aa-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="f46aa-285">2.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f46aa-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="f46aa-286">2.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="f46aa-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="f46aa-287">Ejemplo de respuesta 2.6.2</span><span class="sxs-lookup"><span data-stu-id="f46aa-287">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="f46aa-288">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f46aa-288">See also</span></span>

- [<span data-ttu-id="f46aa-289">Exportar métodos de evaluación y propiedades por dispositivo</span><span class="sxs-lookup"><span data-stu-id="f46aa-289">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="f46aa-290">Exportar evaluación de configuración segura por dispositivo</span><span class="sxs-lookup"><span data-stu-id="f46aa-290">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="f46aa-291">Exportar evaluación de inventario de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="f46aa-291">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

<span data-ttu-id="f46aa-292">Otros relacionados</span><span class="sxs-lookup"><span data-stu-id="f46aa-292">Other related</span></span>

- [<span data-ttu-id="f46aa-293">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="f46aa-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="f46aa-294">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="f46aa-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
