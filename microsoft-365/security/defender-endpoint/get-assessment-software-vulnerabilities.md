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
ms.openlocfilehash: ea05d37ebcd0953dd109f524775a55cf8d6b3683
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984969"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="b4427-105">Evaluación de vulnerabilidades de software de exportación por dispositivo</span><span class="sxs-lookup"><span data-stu-id="b4427-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4427-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b4427-106">**Applies to:**</span></span>

- [<span data-ttu-id="b4427-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b4427-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b4427-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4427-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b4427-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b4427-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b4427-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b4427-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="b4427-111">Devuelve todas las vulnerabilidades de software conocidas y sus detalles para todos los dispositivos, por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="b4427-112">Hay diferentes llamadas API para obtener diferentes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="b4427-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="b4427-113">Dado que la cantidad de datos puede ser muy grande, hay dos formas de recuperarlos:</span><span class="sxs-lookup"><span data-stu-id="b4427-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="b4427-114">[Evaluación de vulnerabilidades de software de exportación de OData](#1-export-software-vulnerabilities-assessment-odata)  La API extrae todos los datos de la organización como respuestas Json, siguiendo el protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="b4427-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="b4427-115">Este método es el mejor para _organizaciones pequeñas con dispositivos de menos de 100 K._</span><span class="sxs-lookup"><span data-stu-id="b4427-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="b4427-116">La respuesta se pagina, por lo que puede usar el campo odata.nextLink de la respuesta \@ para obtener los siguientes resultados.</span><span class="sxs-lookup"><span data-stu-id="b4427-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="b4427-117">[Evaluación de vulnerabilidades de software de exportación a través de archivos](#2-export-software-vulnerabilities-assessment-via-files) Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable.</span><span class="sxs-lookup"><span data-stu-id="b4427-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="b4427-118">Via-files se recomienda para organizaciones grandes, con más de 100 K dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b4427-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="b4427-119">Esta API extrae todos los datos de la organización como archivos de descarga.</span><span class="sxs-lookup"><span data-stu-id="b4427-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="b4427-120">La respuesta contiene direcciones URL para descargar todos los datos de Almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="b4427-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="b4427-121">Esta API le permite descargar todos los datos de Almacenamiento de Azure de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b4427-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="b4427-122">Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="b4427-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="b4427-123">Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.</span><span class="sxs-lookup"><span data-stu-id="b4427-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="b4427-124">[Evaluación de vulnerabilidades de software de exportación delta OData](#3-delta-export-software-vulnerabilities-assessment-odata)  Devuelve una tabla con una entrada para cada combinación única de: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId y EventTimestamp.</span><span class="sxs-lookup"><span data-stu-id="b4427-124">[Delta export software vulnerabilities assessment OData](#3-delta-export-software-vulnerabilities-assessment-odata)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="b4427-125">La API extrae datos de la organización como respuestas Json, siguiendo el protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="b4427-125">The API pulls data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="b4427-126">La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados.</span><span class="sxs-lookup"><span data-stu-id="b4427-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="b4427-127">A diferencia de la evaluación completa de vulnerabilidades de software (OData), que se usa para obtener una instantánea completa de la evaluación de vulnerabilidades de software de su organización por dispositivo, la llamada a la API de OData de exportación delta se usa para capturar solo los cambios que han ocurrido entre una fecha seleccionada y la fecha actual (la llamada a la API "delta").</span><span class="sxs-lookup"><span data-stu-id="b4427-127">Unlike the full software vulnerabilities assessment (OData) - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="b4427-128">En lugar de obtener una exportación completa con una gran cantidad de datos cada vez, solo se obtiene información específica sobre vulnerabilidades nuevas, fijas y actualizadas.</span><span class="sxs-lookup"><span data-stu-id="b4427-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="b4427-129">La llamada a la API de OData de exportación de Delta también se puede usar para calcular diferentes KPI, como "¿cuántas vulnerabilidades se han corregido?".</span><span class="sxs-lookup"><span data-stu-id="b4427-129">Delta export OData API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="b4427-130">o "¿cuántas vulnerabilidades nuevas se agregaron a mi organización?"</span><span class="sxs-lookup"><span data-stu-id="b4427-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="b4427-131">Dado que la llamada de la API de OData de exportación de Delta para vulnerabilidades de software devuelve datos solo para un intervalo de fechas de destino, no se considera una _exportación completa_.</span><span class="sxs-lookup"><span data-stu-id="b4427-131">Because the Delta export OData API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="b4427-132">Los datos recopilados (mediante _OData_ o a través de _archivos)_ son la instantánea actual del estado actual y no contienen datos históricos.</span><span class="sxs-lookup"><span data-stu-id="b4427-132">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="b4427-133">Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.</span><span class="sxs-lookup"><span data-stu-id="b4427-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="b4427-134">A menos que se indique lo \*\*\*\* contrario, todos los métodos de evaluación de exportación enumerados son exportación completa y por **_dispositivo_** (también **_denominados por dispositivo_**).</span><span class="sxs-lookup"><span data-stu-id="b4427-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="b4427-135">1. Evaluación de vulnerabilidades de software de exportación (OData)</span><span class="sxs-lookup"><span data-stu-id="b4427-135">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="b4427-136">Descripción del método de api 1.1</span><span class="sxs-lookup"><span data-stu-id="b4427-136">1.1 API method description</span></span>

<span data-ttu-id="b4427-137">Esta respuesta de la API contiene todos los datos del software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="b4427-138">Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="b4427-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="b4427-139">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="b4427-139">Limitations</span></span>

>- <span data-ttu-id="b4427-140">El tamaño máximo de página es 200 000.</span><span class="sxs-lookup"><span data-stu-id="b4427-140">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="b4427-141">Las limitaciones de velocidad para esta API son 30 llamadas por minuto y 1000 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="b4427-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="b4427-142">1.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="b4427-142">1.2 Permissions</span></span>

<span data-ttu-id="b4427-143">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="b4427-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b4427-144">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b4427-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="b4427-145">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="b4427-145">Permission type</span></span> | <span data-ttu-id="b4427-146">Permiso</span><span class="sxs-lookup"><span data-stu-id="b4427-146">Permission</span></span> | <span data-ttu-id="b4427-147">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="b4427-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="b4427-148">Aplicación</span><span class="sxs-lookup"><span data-stu-id="b4427-148">Application</span></span> | <span data-ttu-id="b4427-149">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="b4427-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="b4427-150">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="b4427-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="b4427-151">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="b4427-151">Delegated (work or school account)</span></span> | <span data-ttu-id="b4427-152">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="b4427-152">Vulnerability.Read</span></span> | <span data-ttu-id="b4427-153">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="b4427-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="b4427-154">DIRECCIÓN URL 1.3</span><span class="sxs-lookup"><span data-stu-id="b4427-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="b4427-155">1.4 Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4427-155">1.4 Parameters</span></span>

- <span data-ttu-id="b4427-156">pageSize (valor predeterminado = 50.000): número de resultados en la respuesta</span><span class="sxs-lookup"><span data-stu-id="b4427-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="b4427-157">$top: número de resultados que se devolverán (no devuelve @odata.nextLink y, por lo tanto, no extrae todos los datos)</span><span class="sxs-lookup"><span data-stu-id="b4427-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="b4427-158">1.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="b4427-158">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="b4427-159">Cada registro tiene aproximadamente 1 KB de datos.</span><span class="sxs-lookup"><span data-stu-id="b4427-159">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="b4427-160">Debe tener esto en cuenta al elegir el parámetro pageSize correcto.</span><span class="sxs-lookup"><span data-stu-id="b4427-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="b4427-161">Es posible que se devuelvan algunas columnas adicionales en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b4427-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="b4427-162">Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.</span><span class="sxs-lookup"><span data-stu-id="b4427-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="b4427-163">Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b4427-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="b4427-164">Al ejecutar esta API, el resultado resultante no se devolverá necesariamente en el mismo orden enumerado en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="b4427-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="b4427-165">Propiedad (ID)</span><span class="sxs-lookup"><span data-stu-id="b4427-165">Property (ID)</span></span> | <span data-ttu-id="b4427-166">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b4427-166">Data type</span></span> | <span data-ttu-id="b4427-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4427-167">Description</span></span> | <span data-ttu-id="b4427-168">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4427-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="b4427-169">CveId</span><span class="sxs-lookup"><span data-stu-id="b4427-169">CveId</span></span> | <span data-ttu-id="b4427-170">string</span><span class="sxs-lookup"><span data-stu-id="b4427-170">string</span></span> | <span data-ttu-id="b4427-171">Identificador único asignado a la vulnerabilidad de seguridad en el sistema vulnerabilidades y exposiciones comunes (CVE).</span><span class="sxs-lookup"><span data-stu-id="b4427-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="b4427-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="b4427-172">CVE-2020-15992</span></span>
<span data-ttu-id="b4427-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="b4427-173">CvssScore</span></span> | <span data-ttu-id="b4427-174">string</span><span class="sxs-lookup"><span data-stu-id="b4427-174">string</span></span> | <span data-ttu-id="b4427-175">La puntuación CVSS de CVE.</span><span class="sxs-lookup"><span data-stu-id="b4427-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="b4427-176">6.2</span><span class="sxs-lookup"><span data-stu-id="b4427-176">6.2</span></span>
<span data-ttu-id="b4427-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="b4427-177">DeviceId</span></span> | <span data-ttu-id="b4427-178">string</span><span class="sxs-lookup"><span data-stu-id="b4427-178">string</span></span> | <span data-ttu-id="b4427-179">Identificador único del dispositivo en el servicio.</span><span class="sxs-lookup"><span data-stu-id="b4427-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="b4427-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="b4427-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="b4427-181">DeviceName</span><span class="sxs-lookup"><span data-stu-id="b4427-181">DeviceName</span></span> | <span data-ttu-id="b4427-182">string</span><span class="sxs-lookup"><span data-stu-id="b4427-182">string</span></span> | <span data-ttu-id="b4427-183">Nombre de dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="b4427-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4427-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="b4427-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="b4427-185">DiskPaths</span></span>  | <span data-ttu-id="b4427-186">Cadena de \[ matriz\]</span><span class="sxs-lookup"><span data-stu-id="b4427-186">Array\[string\]</span></span> | <span data-ttu-id="b4427-187">Prueba en disco de que el producto está instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="b4427-188">[ "C:\Archivos de programa (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="b4427-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="b4427-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="b4427-189">ExploitabilityLevel</span></span> | <span data-ttu-id="b4427-190">string</span><span class="sxs-lookup"><span data-stu-id="b4427-190">string</span></span> | <span data-ttu-id="b4427-191">El nivel de vulnerabilidad de esta vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="b4427-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="b4427-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="b4427-192">ExploitIsInKit</span></span>
<span data-ttu-id="b4427-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="b4427-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="b4427-194">string</span><span class="sxs-lookup"><span data-stu-id="b4427-194">string</span></span> | <span data-ttu-id="b4427-195">Primera vez que se vio la CVE de este producto en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="b4427-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="b4427-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="b4427-197">Id</span><span class="sxs-lookup"><span data-stu-id="b4427-197">Id</span></span> | <span data-ttu-id="b4427-198">string</span><span class="sxs-lookup"><span data-stu-id="b4427-198">string</span></span> | <span data-ttu-id="b4427-199">Identificador único del registro.</span><span class="sxs-lookup"><span data-stu-id="b4427-199">Unique identifier for the record.</span></span> | <span data-ttu-id="b4427-200">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="b4427-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="b4427-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="b4427-201">LastSeenTimestamp</span></span> | <span data-ttu-id="b4427-202">string</span><span class="sxs-lookup"><span data-stu-id="b4427-202">string</span></span> | <span data-ttu-id="b4427-203">La última vez que se vio CVE en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="b4427-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="b4427-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="b4427-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="b4427-205">OSPlatform</span></span> | <span data-ttu-id="b4427-206">string</span><span class="sxs-lookup"><span data-stu-id="b4427-206">string</span></span> | <span data-ttu-id="b4427-207">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="b4427-208">Esta propiedad indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b4427-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="b4427-209">Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b4427-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="b4427-210">Windows10</span><span class="sxs-lookup"><span data-stu-id="b4427-210">Windows10</span></span>
<span data-ttu-id="b4427-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="b4427-211">RbacGroupName</span></span>  | <span data-ttu-id="b4427-212">string</span><span class="sxs-lookup"><span data-stu-id="b4427-212">string</span></span> | <span data-ttu-id="b4427-213">Grupo de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b4427-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="b4427-214">Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="b4427-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="b4427-215">Si la organización no contiene ningún grupo RBAC, el valor será "None".</span><span class="sxs-lookup"><span data-stu-id="b4427-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="b4427-216">Servidores</span><span class="sxs-lookup"><span data-stu-id="b4427-216">Servers</span></span>
<span data-ttu-id="b4427-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="b4427-217">RecommendationReference</span></span> | <span data-ttu-id="b4427-218">string</span><span class="sxs-lookup"><span data-stu-id="b4427-218">string</span></span> | <span data-ttu-id="b4427-219">Una referencia al identificador de recomendación relacionado con este software.</span><span class="sxs-lookup"><span data-stu-id="b4427-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="b4427-220">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="b4427-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="b4427-221">RecommendedSecurityUpdate (opcional)</span><span class="sxs-lookup"><span data-stu-id="b4427-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="b4427-222">string</span><span class="sxs-lookup"><span data-stu-id="b4427-222">string</span></span> | <span data-ttu-id="b4427-223">Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="b4427-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="b4427-224">Actualizaciones de seguridad de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="b4427-224">April 2020 Security Updates</span></span>
<span data-ttu-id="b4427-225">RecommendedSecurityUpdateId (opcional)</span><span class="sxs-lookup"><span data-stu-id="b4427-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="b4427-226">string</span><span class="sxs-lookup"><span data-stu-id="b4427-226">string</span></span> | <span data-ttu-id="b4427-227">Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes</span><span class="sxs-lookup"><span data-stu-id="b4427-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="b4427-228">4550961</span><span class="sxs-lookup"><span data-stu-id="b4427-228">4550961</span></span>
<span data-ttu-id="b4427-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="b4427-229">RegistryPaths</span></span>  | <span data-ttu-id="b4427-230">Cadena de \[ matriz\]</span><span class="sxs-lookup"><span data-stu-id="b4427-230">Array\[string\]</span></span> | <span data-ttu-id="b4427-231">El Registro evidencia que el producto está instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="b4427-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="b4427-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="b4427-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="b4427-233">SoftwareName</span></span> | <span data-ttu-id="b4427-234">string</span><span class="sxs-lookup"><span data-stu-id="b4427-234">string</span></span> | <span data-ttu-id="b4427-235">Nombre del producto de software.</span><span class="sxs-lookup"><span data-stu-id="b4427-235">Name of the software product.</span></span> | <span data-ttu-id="b4427-236">chrome</span><span class="sxs-lookup"><span data-stu-id="b4427-236">chrome</span></span>
<span data-ttu-id="b4427-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="b4427-237">SoftwareVendor</span></span> | <span data-ttu-id="b4427-238">string</span><span class="sxs-lookup"><span data-stu-id="b4427-238">string</span></span> | <span data-ttu-id="b4427-239">Nombre del proveedor de software.</span><span class="sxs-lookup"><span data-stu-id="b4427-239">Name of the software vendor.</span></span> | <span data-ttu-id="b4427-240">google</span><span class="sxs-lookup"><span data-stu-id="b4427-240">google</span></span>
<span data-ttu-id="b4427-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="b4427-241">SoftwareVersion</span></span> | <span data-ttu-id="b4427-242">string</span><span class="sxs-lookup"><span data-stu-id="b4427-242">string</span></span> | <span data-ttu-id="b4427-243">Número de versión del producto de software.</span><span class="sxs-lookup"><span data-stu-id="b4427-243">Version number of the software product.</span></span> | <span data-ttu-id="b4427-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="b4427-244">81.0.4044.138</span></span>
<span data-ttu-id="b4427-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="b4427-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="b4427-246">string</span><span class="sxs-lookup"><span data-stu-id="b4427-246">string</span></span> | <span data-ttu-id="b4427-247">Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS y los factores dinámicos influenciados por el panorama de amenazas.</span><span class="sxs-lookup"><span data-stu-id="b4427-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="b4427-248">Medio</span><span class="sxs-lookup"><span data-stu-id="b4427-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="b4427-249">1.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b4427-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="b4427-250">1.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="b4427-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="b4427-251">Ejemplo de respuesta 1.6.2</span><span class="sxs-lookup"><span data-stu-id="b4427-251">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="b4427-252">2. Evaluación de vulnerabilidades de software de exportación (a través de archivos)</span><span class="sxs-lookup"><span data-stu-id="b4427-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="b4427-253">Descripción del método api 2.1</span><span class="sxs-lookup"><span data-stu-id="b4427-253">2.1 API method description</span></span>

<span data-ttu-id="b4427-254">Esta respuesta de la API contiene todos los datos del software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="b4427-255">Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="b4427-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="b4427-256">2.1.2 Limitaciones</span><span class="sxs-lookup"><span data-stu-id="b4427-256">2.1.2 Limitations</span></span>

<span data-ttu-id="b4427-257">Las limitaciones de velocidad para esta API son 5 llamadas por minuto y 20 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="b4427-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="b4427-258">2.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="b4427-258">2.2 Permissions</span></span>

<span data-ttu-id="b4427-259">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="b4427-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b4427-260">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b4427-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="b4427-261">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="b4427-261">Permission type</span></span> | <span data-ttu-id="b4427-262">Permiso</span><span class="sxs-lookup"><span data-stu-id="b4427-262">Permission</span></span> | <span data-ttu-id="b4427-263">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="b4427-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="b4427-264">Aplicación</span><span class="sxs-lookup"><span data-stu-id="b4427-264">Application</span></span> | <span data-ttu-id="b4427-265">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="b4427-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="b4427-266">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="b4427-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="b4427-267">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="b4427-267">Delegated (work or school account)</span></span> | <span data-ttu-id="b4427-268">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="b4427-268">Vulnerability.Read</span></span> | <span data-ttu-id="b4427-269">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="b4427-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="b4427-270">DIRECCIÓN URL 2.3</span><span class="sxs-lookup"><span data-stu-id="b4427-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="b4427-271">Parámetros 2.4</span><span class="sxs-lookup"><span data-stu-id="b4427-271">2.4 Parameters</span></span>

- <span data-ttu-id="b4427-272">sasValidHours: el número de horas durante las que las direcciones URL de descarga serán válidas (máximo 24 horas)</span><span class="sxs-lookup"><span data-stu-id="b4427-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="b4427-273">2.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="b4427-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="b4427-274">Los archivos son archivos comprimidos de gzip & en formato Json de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="b4427-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="b4427-275">Las direcciones URL de descarga solo son válidas durante 3 horas; de lo contrario, puede usar el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b4427-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="b4427-276">Para obtener la velocidad máxima de descarga de los datos, puede asegurarse de que está descargando desde la misma región de Azure en la que residen los datos.</span><span class="sxs-lookup"><span data-stu-id="b4427-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="b4427-277">Cada registro tiene aproximadamente 1 KB de datos.</span><span class="sxs-lookup"><span data-stu-id="b4427-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="b4427-278">Debe tener esto en cuenta al elegir el parámetro pageSize correcto.</span><span class="sxs-lookup"><span data-stu-id="b4427-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="b4427-279">Es posible que se devuelvan algunas columnas adicionales en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b4427-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="b4427-280">Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.</span><span class="sxs-lookup"><span data-stu-id="b4427-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="b4427-281">Propiedad (ID)</span><span class="sxs-lookup"><span data-stu-id="b4427-281">Property (ID)</span></span> | <span data-ttu-id="b4427-282">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b4427-282">Data type</span></span> | <span data-ttu-id="b4427-283">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4427-283">Description</span></span> | <span data-ttu-id="b4427-284">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4427-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="b4427-285">Exportar archivos</span><span class="sxs-lookup"><span data-stu-id="b4427-285">Export files</span></span> | <span data-ttu-id="b4427-286">cadena de \[ matriz\]</span><span class="sxs-lookup"><span data-stu-id="b4427-286">array\[string\]</span></span>  | <span data-ttu-id="b4427-287">Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización.</span><span class="sxs-lookup"><span data-stu-id="b4427-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="b4427-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="b4427-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="b4427-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="b4427-289">GeneratedTime</span></span> | <span data-ttu-id="b4427-290">string</span><span class="sxs-lookup"><span data-stu-id="b4427-290">string</span></span> | <span data-ttu-id="b4427-291">Hora en que se generó la exportación.</span><span class="sxs-lookup"><span data-stu-id="b4427-291">The time that the export was generated.</span></span> | <span data-ttu-id="b4427-292">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="b4427-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="b4427-293">2.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b4427-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="b4427-294">2.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="b4427-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="b4427-295">Ejemplo de respuesta 2.6.2</span><span class="sxs-lookup"><span data-stu-id="b4427-295">2.6.2 Response example</span></span>

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

## <a name="3-delta-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="b4427-296">3. Evaluación de vulnerabilidades de software de exportación delta (OData)</span><span class="sxs-lookup"><span data-stu-id="b4427-296">3. Delta export software vulnerabilities assessment (OData)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="b4427-297">Descripción del método de api 3.1</span><span class="sxs-lookup"><span data-stu-id="b4427-297">3.1 API method description</span></span>

<span data-ttu-id="b4427-298">Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span><span class="sxs-lookup"><span data-stu-id="b4427-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="b4427-299">La API extrae datos de la organización como respuestas Json, siguiendo el protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="b4427-299">The API pulls data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="b4427-300">La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados.</span><span class="sxs-lookup"><span data-stu-id="b4427-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="b4427-301">A diferencia de la evaluación completa de vulnerabilidades de software (OData), que se usa para obtener una instantánea completa de la evaluación de vulnerabilidades de software de su organización por dispositivo, la llamada a la API de OData de exportación delta se usa para capturar solo los cambios que han ocurrido entre una fecha seleccionada y la fecha actual (la llamada a la API "delta").</span><span class="sxs-lookup"><span data-stu-id="b4427-301">Unlike the full software vulnerabilities assessment (OData) - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export  OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="b4427-302">En lugar de obtener una exportación completa con una gran cantidad de datos cada vez, solo se obtiene información específica sobre vulnerabilidades nuevas, fijas y actualizadas.</span><span class="sxs-lookup"><span data-stu-id="b4427-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="b4427-303">La llamada a la API de OData de exportación de Delta también se puede usar para calcular diferentes KPI, como "¿cuántas vulnerabilidades se han corregido?".</span><span class="sxs-lookup"><span data-stu-id="b4427-303">Delta export OData API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="b4427-304">o "¿cuántas vulnerabilidades nuevas se agregaron a mi organización?"</span><span class="sxs-lookup"><span data-stu-id="b4427-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="b4427-305">Es muy recomendable que use la evaluación completa de vulnerabilidades de software de exportación por llamada api de dispositivo al menos una vez a la semana, y esta vulnerabilidad de software de exportación adicional cambia por API de dispositivo (delta) llamar a todos los demás días de la semana.</span><span class="sxs-lookup"><span data-stu-id="b4427-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="b4427-306">A diferencia de la otra API de OData de evaluaciones, la "exportación delta" no es una exportación completa.</span><span class="sxs-lookup"><span data-stu-id="b4427-306">Unlike the other Assessments OData API, the “delta export” is not a full export.</span></span> <span data-ttu-id="b4427-307">La exportación delta incluye solo los cambios que se han producido entre una fecha seleccionada y la fecha actual (la llamada a la API "delta").</span><span class="sxs-lookup"><span data-stu-id="b4427-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="limitations"></a><span data-ttu-id="b4427-308">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="b4427-308">Limitations</span></span>

- <span data-ttu-id="b4427-309">El tamaño máximo de página es 200 000.</span><span class="sxs-lookup"><span data-stu-id="b4427-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="b4427-310">El parámetro sinceTime tiene un máximo de 14 días.</span><span class="sxs-lookup"><span data-stu-id="b4427-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="b4427-311">Las limitaciones de velocidad para esta API son 30 llamadas por minuto y 1000 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="b4427-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="b4427-312">3.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="b4427-312">3.2 Permissions</span></span>

<span data-ttu-id="b4427-313">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="b4427-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b4427-314">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b4427-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="b4427-315">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="b4427-315">Permission type</span></span> | <span data-ttu-id="b4427-316">Permiso</span><span class="sxs-lookup"><span data-stu-id="b4427-316">Permission</span></span> | <span data-ttu-id="b4427-317">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="b4427-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="b4427-318">Aplicación</span><span class="sxs-lookup"><span data-stu-id="b4427-318">Application</span></span> | <span data-ttu-id="b4427-319">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="b4427-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="b4427-320">'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b4427-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="b4427-321">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="b4427-321">Delegated (work or school account)</span></span> | <span data-ttu-id="b4427-322">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="b4427-322">Vulnerability.Read</span></span> | <span data-ttu-id="b4427-323">'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b4427-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="b4427-324">DIRECCIÓN URL 3.3</span><span class="sxs-lookup"><span data-stu-id="b4427-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="b4427-325">Parámetros 3.4</span><span class="sxs-lookup"><span data-stu-id="b4427-325">3.4 Parameters</span></span>

- <span data-ttu-id="b4427-326">sinceTime (obligatorio): los datos entre una hora seleccionada y la actualidad.</span><span class="sxs-lookup"><span data-stu-id="b4427-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="b4427-327">pageSize (valor predeterminado = 50.000): número de resultados en la respuesta</span><span class="sxs-lookup"><span data-stu-id="b4427-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="b4427-328">$top: número de resultados que se devolverán (no devuelve @odata.nextLink y, por lo tanto, no extrae todos los datos)</span><span class="sxs-lookup"><span data-stu-id="b4427-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="b4427-329">3.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="b4427-329">3.5 Properties</span></span>

<span data-ttu-id="b4427-330">Cada registro devuelto contiene todos los datos de la evaluación completa de vulnerabilidades de software de exportación por parte de la API de OData del dispositivo, además de dos campos adicionales:  _**EventTimestamp**_ y _**Status**_.</span><span class="sxs-lookup"><span data-stu-id="b4427-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device OData API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
><span data-ttu-id="b4427-331">-Es posible que se devuelvan algunas columnas adicionales en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b4427-331">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="b4427-332">Estas columnas son temporales y pueden quitarse, por lo que use solo las columnas documentadas.</span><span class="sxs-lookup"><span data-stu-id="b4427-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
><span data-ttu-id="b4427-333">-Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b4427-333">-The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="b4427-334">Al ejecutar esta API, el resultado resultante no se devolverá necesariamente en el mismo orden enumerado en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="b4427-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br>

<span data-ttu-id="b4427-335">Propiedad (ID)</span><span class="sxs-lookup"><span data-stu-id="b4427-335">Property (ID)</span></span> | <span data-ttu-id="b4427-336">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b4427-336">Data type</span></span> | <span data-ttu-id="b4427-337">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4427-337">Description</span></span> | <span data-ttu-id="b4427-338">Ejemplo del valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4427-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="b4427-339">CveId</span><span class="sxs-lookup"><span data-stu-id="b4427-339">CveId</span></span> | <span data-ttu-id="b4427-340">string</span><span class="sxs-lookup"><span data-stu-id="b4427-340">string</span></span> | <span data-ttu-id="b4427-341">Identificador único asignado a la vulnerabilidad de seguridad en el sistema vulnerabilidades y exposiciones comunes (CVE).</span><span class="sxs-lookup"><span data-stu-id="b4427-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="b4427-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="b4427-342">CVE-2020-15992</span></span>  
<span data-ttu-id="b4427-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="b4427-343">CvssScore</span></span> | <span data-ttu-id="b4427-344">string</span><span class="sxs-lookup"><span data-stu-id="b4427-344">string</span></span> | <span data-ttu-id="b4427-345">La puntuación CVSS de CVE.</span><span class="sxs-lookup"><span data-stu-id="b4427-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="b4427-346">6.2</span><span class="sxs-lookup"><span data-stu-id="b4427-346">6.2</span></span>  
<span data-ttu-id="b4427-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="b4427-347">DeviceId</span></span> | <span data-ttu-id="b4427-348">string</span><span class="sxs-lookup"><span data-stu-id="b4427-348">string</span></span> | <span data-ttu-id="b4427-349">Identificador único del dispositivo en el servicio.</span><span class="sxs-lookup"><span data-stu-id="b4427-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="b4427-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="b4427-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="b4427-351">DeviceName</span><span class="sxs-lookup"><span data-stu-id="b4427-351">DeviceName</span></span> | <span data-ttu-id="b4427-352">string</span><span class="sxs-lookup"><span data-stu-id="b4427-352">string</span></span> | <span data-ttu-id="b4427-353">Nombre de dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="b4427-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4427-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="b4427-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="b4427-355">DiskPaths</span></span> | <span data-ttu-id="b4427-356">Array[string]</span><span class="sxs-lookup"><span data-stu-id="b4427-356">Array[string]</span></span> | <span data-ttu-id="b4427-357">Prueba en disco de que el producto está instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="b4427-358">[ "C:\Archivos de programa (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="b4427-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="b4427-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="b4427-359">EventTimestamp</span></span> | <span data-ttu-id="b4427-360">String</span><span class="sxs-lookup"><span data-stu-id="b4427-360">String</span></span> | <span data-ttu-id="b4427-361">Hora en que se encontró este evento delta.</span><span class="sxs-lookup"><span data-stu-id="b4427-361">The time this delta event was found.</span></span> | <span data-ttu-id="b4427-362">2021-01-11T11:06:08.291Z</span><span class="sxs-lookup"><span data-stu-id="b4427-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="b4427-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="b4427-363">ExploitabilityLevel</span></span> | <span data-ttu-id="b4427-364">string</span><span class="sxs-lookup"><span data-stu-id="b4427-364">string</span></span> | <span data-ttu-id="b4427-365">El nivel de vulnerabilidad de esta vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="b4427-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="b4427-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="b4427-366">ExploitIsInKit</span></span>  
<span data-ttu-id="b4427-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="b4427-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="b4427-368">string</span><span class="sxs-lookup"><span data-stu-id="b4427-368">string</span></span> | <span data-ttu-id="b4427-369">Primera vez que se vio la CVE de este producto en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="b4427-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="b4427-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="b4427-371">Id</span><span class="sxs-lookup"><span data-stu-id="b4427-371">Id</span></span> | <span data-ttu-id="b4427-372">string</span><span class="sxs-lookup"><span data-stu-id="b4427-372">string</span></span> | <span data-ttu-id="b4427-373">Identificador único del registro.</span><span class="sxs-lookup"><span data-stu-id="b4427-373">Unique identifier for the record.</span></span> | <span data-ttu-id="b4427-374">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="b4427-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="b4427-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="b4427-375">LastSeenTimestamp</span></span> | <span data-ttu-id="b4427-376">string</span><span class="sxs-lookup"><span data-stu-id="b4427-376">string</span></span> | <span data-ttu-id="b4427-377">La última vez que se vio CVE en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="b4427-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="b4427-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="b4427-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="b4427-379">OSPlatform</span></span> | <span data-ttu-id="b4427-380">string</span><span class="sxs-lookup"><span data-stu-id="b4427-380">string</span></span> | <span data-ttu-id="b4427-381">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="b4427-382">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b4427-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="b4427-383">Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b4427-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="b4427-384">Windows10</span><span class="sxs-lookup"><span data-stu-id="b4427-384">Windows10</span></span>  
<span data-ttu-id="b4427-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="b4427-385">RbacGroupName</span></span> | <span data-ttu-id="b4427-386">string</span><span class="sxs-lookup"><span data-stu-id="b4427-386">string</span></span> | <span data-ttu-id="b4427-387">Grupo de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b4427-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="b4427-388">Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="b4427-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="b4427-389">Si la organización no contiene ningún grupo RBAC, el valor será "None".</span><span class="sxs-lookup"><span data-stu-id="b4427-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="b4427-390">Servidores</span><span class="sxs-lookup"><span data-stu-id="b4427-390">Servers</span></span>  
<span data-ttu-id="b4427-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="b4427-391">RecommendationReference</span></span> | <span data-ttu-id="b4427-392">string</span><span class="sxs-lookup"><span data-stu-id="b4427-392">string</span></span> | <span data-ttu-id="b4427-393">Una referencia al identificador de recomendación relacionado con este software.</span><span class="sxs-lookup"><span data-stu-id="b4427-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="b4427-394">va--microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="b4427-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="b4427-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="b4427-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="b4427-396">string</span><span class="sxs-lookup"><span data-stu-id="b4427-396">string</span></span> | <span data-ttu-id="b4427-397">Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="b4427-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="b4427-398">Actualizaciones de seguridad de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="b4427-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="b4427-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="b4427-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="b4427-400">string</span><span class="sxs-lookup"><span data-stu-id="b4427-400">string</span></span> | <span data-ttu-id="b4427-401">Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes</span><span class="sxs-lookup"><span data-stu-id="b4427-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="b4427-402">4550961</span><span class="sxs-lookup"><span data-stu-id="b4427-402">4550961</span></span>  
<span data-ttu-id="b4427-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="b4427-403">RegistryPaths</span></span>  | <span data-ttu-id="b4427-404">Array[string]</span><span class="sxs-lookup"><span data-stu-id="b4427-404">Array[string]</span></span> | <span data-ttu-id="b4427-405">El Registro evidencia que el producto está instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="b4427-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span><span class="sxs-lookup"><span data-stu-id="b4427-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="b4427-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="b4427-407">SoftwareName</span></span> | <span data-ttu-id="b4427-408">string</span><span class="sxs-lookup"><span data-stu-id="b4427-408">string</span></span> | <span data-ttu-id="b4427-409">Nombre del producto de software.</span><span class="sxs-lookup"><span data-stu-id="b4427-409">Name of the software product.</span></span> | <span data-ttu-id="b4427-410">chrome</span><span class="sxs-lookup"><span data-stu-id="b4427-410">chrome</span></span>  
<span data-ttu-id="b4427-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="b4427-411">SoftwareVendor</span></span> | <span data-ttu-id="b4427-412">string</span><span class="sxs-lookup"><span data-stu-id="b4427-412">string</span></span> | <span data-ttu-id="b4427-413">Nombre del proveedor de software.</span><span class="sxs-lookup"><span data-stu-id="b4427-413">Name of the software vendor.</span></span> | <span data-ttu-id="b4427-414">google</span><span class="sxs-lookup"><span data-stu-id="b4427-414">google</span></span>  
<span data-ttu-id="b4427-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="b4427-415">SoftwareVersion</span></span> | <span data-ttu-id="b4427-416">string</span><span class="sxs-lookup"><span data-stu-id="b4427-416">string</span></span> | <span data-ttu-id="b4427-417">Número de versión del producto de software.</span><span class="sxs-lookup"><span data-stu-id="b4427-417">Version number of the software product.</span></span> | <span data-ttu-id="b4427-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="b4427-418">81.0.4044.138</span></span>  
<span data-ttu-id="b4427-419">Estado</span><span class="sxs-lookup"><span data-stu-id="b4427-419">Status</span></span> | <span data-ttu-id="b4427-420">String</span><span class="sxs-lookup"><span data-stu-id="b4427-420">String</span></span> | <span data-ttu-id="b4427-421">**Nuevo**   (para una nueva vulnerabilidad introducida en un dispositivo)  (1) **Corregido**(si esta vulnerabilidad ya no existe en el dispositivo, lo que   significa que se corrigió).</span><span class="sxs-lookup"><span data-stu-id="b4427-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="b4427-422">(2)  **Actualizado**   (si ha cambiado una vulnerabilidad en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b4427-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="b4427-423">Los posibles cambios son: puntuación CVSS, nivel de vulnerabilidad, nivel de gravedad, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span><span class="sxs-lookup"><span data-stu-id="b4427-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="b4427-424">Decimal</span><span class="sxs-lookup"><span data-stu-id="b4427-424">Fixed</span></span>
<span data-ttu-id="b4427-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="b4427-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="b4427-426">string</span><span class="sxs-lookup"><span data-stu-id="b4427-426">string</span></span> | <span data-ttu-id="b4427-427">Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS y los factores dinámicos influenciados por el panorama de amenazas.</span><span class="sxs-lookup"><span data-stu-id="b4427-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="b4427-428">Medio</span><span class="sxs-lookup"><span data-stu-id="b4427-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="b4427-429">Aclaraciones</span><span class="sxs-lookup"><span data-stu-id="b4427-429">Clarifications</span></span>

- <span data-ttu-id="b4427-430">Si el software se actualizó de la versión 1.0 a la versión 2.0 y ambas versiones se exponen a CVE-A, recibirás 2 eventos independientes:</span><span class="sxs-lookup"><span data-stu-id="b4427-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   <span data-ttu-id="b4427-431">a.</span><span class="sxs-lookup"><span data-stu-id="b4427-431">a.</span></span> <span data-ttu-id="b4427-432">Corregido: CVE-A en la versión 1.0 era fijo</span><span class="sxs-lookup"><span data-stu-id="b4427-432">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   <span data-ttu-id="b4427-433">b.</span><span class="sxs-lookup"><span data-stu-id="b4427-433">b.</span></span> <span data-ttu-id="b4427-434">Nuevo: se agregó CVE-A en la versión 2.0</span><span class="sxs-lookup"><span data-stu-id="b4427-434">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="b4427-435">Si una vulnerabilidad específica (por ejemplo, CVE-A) se vio por primera vez en un momento específico (por ejemplo, el 10 de enero) en software con la versión 1.0 y unos días más tarde ese software se actualizó a la versión 2.0, que también se expone a la misma CVE-A, recibirá estos dos eventos separados:</span><span class="sxs-lookup"><span data-stu-id="b4427-435">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   <span data-ttu-id="b4427-436">a.</span><span class="sxs-lookup"><span data-stu-id="b4427-436">a.</span></span> <span data-ttu-id="b4427-437">Corregido: CVE-X, FirstSeenTimestamp el 10 de enero, versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="b4427-437">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   <span data-ttu-id="b4427-438">b.</span><span class="sxs-lookup"><span data-stu-id="b4427-438">b.</span></span> <span data-ttu-id="b4427-439">Nuevo: CVE-X, FirstSeenTimestamp el 10 de enero, versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="b4427-439">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="b4427-440">3.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b4427-440">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="b4427-441">Ejemplo de solicitud 3.6.1</span><span class="sxs-lookup"><span data-stu-id="b4427-441">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="b4427-442">Ejemplo de respuesta 3.6.2</span><span class="sxs-lookup"><span data-stu-id="b4427-442">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="b4427-443">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4427-443">See also</span></span>

- [<span data-ttu-id="b4427-444">Exportar métodos de evaluación y propiedades por dispositivo</span><span class="sxs-lookup"><span data-stu-id="b4427-444">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="b4427-445">Exportar evaluación de configuración segura por dispositivo</span><span class="sxs-lookup"><span data-stu-id="b4427-445">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="b4427-446">Exportar evaluación de inventario de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="b4427-446">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="b4427-447">Otros relacionados</span><span class="sxs-lookup"><span data-stu-id="b4427-447">Other related</span></span>

- [<span data-ttu-id="b4427-448">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="b4427-448">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="b4427-449">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="b4427-449">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
