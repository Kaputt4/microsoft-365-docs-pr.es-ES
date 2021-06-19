---
title: Exportar evaluación de configuración segura por dispositivo
description: Devuelve una entrada para cada combinación única de DeviceId, ConfigurationId.
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
ms.openlocfilehash: ad8b2030da4fb4815eb71ca53fb2dbac67a05d79
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022395"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="20060-104">Exportar evaluación de configuración segura por dispositivo</span><span class="sxs-lookup"><span data-stu-id="20060-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="20060-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="20060-105">**Applies to:**</span></span>

- [<span data-ttu-id="20060-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="20060-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="20060-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20060-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="20060-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="20060-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="20060-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="20060-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="20060-110">Devuelve todas las configuraciones y su estado, por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20060-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="20060-111">Hay diferentes llamadas API para obtener diferentes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="20060-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="20060-112">Dado que la cantidad de datos puede ser grande, hay dos formas de recuperarlos:</span><span class="sxs-lookup"><span data-stu-id="20060-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="20060-113">[Exportar respuesta **JSON** de evaluación de](#1-export-secure-configuration-assessment-json-response)configuración segura: la API extrae todos los datos de la organización como respuestas Json.</span><span class="sxs-lookup"><span data-stu-id="20060-113">[Export secure configuration assessment **JSON response**](#1-export-secure-configuration-assessment-json-response):  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="20060-114">Este método es el mejor para organizaciones pequeñas con dispositivos de menos de _100 K._</span><span class="sxs-lookup"><span data-stu-id="20060-114">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="20060-115">La respuesta se pagina, por lo que puede usar el campo odata.nextLink de la respuesta \@ para obtener los siguientes resultados.</span><span class="sxs-lookup"><span data-stu-id="20060-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="20060-116">[Exportar la evaluación de configuración **segura a través**](#2-export-secure-configuration-assessment-via-files)de archivos: esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable.</span><span class="sxs-lookup"><span data-stu-id="20060-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="20060-117">Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos.</span><span class="sxs-lookup"><span data-stu-id="20060-117">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="20060-118">Esta API extrae todos los datos de la organización como archivos de descarga.</span><span class="sxs-lookup"><span data-stu-id="20060-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="20060-119">La respuesta contiene direcciones URL para descargar todos los datos de Almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="20060-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="20060-120">Esta API le permite descargar todos los datos de Almacenamiento de Azure de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="20060-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="20060-121">Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="20060-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="20060-122">Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.</span><span class="sxs-lookup"><span data-stu-id="20060-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="20060-123">Los datos recopilados (mediante _OData_ o a través de _archivos)_ son la instantánea actual del estado actual y no contienen datos históricos.</span><span class="sxs-lookup"><span data-stu-id="20060-123">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="20060-124">Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.</span><span class="sxs-lookup"><span data-stu-id="20060-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="20060-125">A menos que se indique lo \*\*\*\* contrario, todos los métodos de evaluación de exportación enumerados son exportación completa y por **_dispositivo_** (también **_denominados por dispositivo_**).</span><span class="sxs-lookup"><span data-stu-id="20060-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-json-response"></a><span data-ttu-id="20060-126">1. Exportar evaluación de configuración segura (respuesta JSON)</span><span class="sxs-lookup"><span data-stu-id="20060-126">1. Export secure configuration assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="20060-127">Descripción del método de api 1.1</span><span class="sxs-lookup"><span data-stu-id="20060-127">1.1 API method description</span></span>

<span data-ttu-id="20060-128">Esta respuesta de la API contiene la evaluación de configuración segura en los dispositivos expuestos y devuelve una entrada para cada combinación única de DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="20060-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="20060-129">1.1.1 Limitaciones</span><span class="sxs-lookup"><span data-stu-id="20060-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="20060-130">El tamaño máximo de página es 200 000.</span><span class="sxs-lookup"><span data-stu-id="20060-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="20060-131">Las limitaciones de velocidad para esta API son 30 llamadas por minuto y 1000 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="20060-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="20060-132">1.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="20060-132">1.2 Permissions</span></span>

<span data-ttu-id="20060-133">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="20060-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="20060-134">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="20060-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="20060-135">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="20060-135">Permission type</span></span> | <span data-ttu-id="20060-136">Permiso</span><span class="sxs-lookup"><span data-stu-id="20060-136">Permission</span></span> | <span data-ttu-id="20060-137">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="20060-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="20060-138">Aplicación</span><span class="sxs-lookup"><span data-stu-id="20060-138">Application</span></span> | <span data-ttu-id="20060-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="20060-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="20060-140">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="20060-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="20060-141">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="20060-141">Delegated (work or school account)</span></span> | <span data-ttu-id="20060-142">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="20060-142">Vulnerability.Read</span></span> | <span data-ttu-id="20060-143">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="20060-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="20060-144">DIRECCIÓN URL 1.3</span><span class="sxs-lookup"><span data-stu-id="20060-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="20060-145">1.4 Parámetros</span><span class="sxs-lookup"><span data-stu-id="20060-145">1.4 Parameters</span></span>

- <span data-ttu-id="20060-146">pageSize \( predeterminado = 50.000: \) número de resultados en la respuesta</span><span class="sxs-lookup"><span data-stu-id="20060-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="20060-147">\$top: el número de resultados que se devolverán no \( devuelve odata.nextLink y, por lo tanto, \@ no extrae todos los datos\)</span><span class="sxs-lookup"><span data-stu-id="20060-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="20060-148">1.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="20060-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="20060-149">Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="20060-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="20060-150">Al ejecutar esta API, el resultado resultante no se devolverá necesariamente en el mismo orden enumerado en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="20060-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="20060-151">Es posible que se devuelvan algunas columnas adicionales en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="20060-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="20060-152">Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.</span><span class="sxs-lookup"><span data-stu-id="20060-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="20060-153">Propiedad (ID)</span><span class="sxs-lookup"><span data-stu-id="20060-153">Property (ID)</span></span> | <span data-ttu-id="20060-154">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="20060-154">Data type</span></span> | <span data-ttu-id="20060-155">Description</span><span class="sxs-lookup"><span data-stu-id="20060-155">Description</span></span> | <span data-ttu-id="20060-156">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20060-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="20060-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="20060-157">ConfigurationCategory</span></span> | <span data-ttu-id="20060-158">string</span><span class="sxs-lookup"><span data-stu-id="20060-158">string</span></span> | <span data-ttu-id="20060-159">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="20060-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="20060-160">Controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="20060-160">Security controls</span></span>
<span data-ttu-id="20060-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="20060-161">ConfigurationId</span></span> | <span data-ttu-id="20060-162">string</span><span class="sxs-lookup"><span data-stu-id="20060-162">string</span></span> | <span data-ttu-id="20060-163">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="20060-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="20060-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="20060-164">scid-10000</span></span>
<span data-ttu-id="20060-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="20060-165">ConfigurationImpact</span></span> | <span data-ttu-id="20060-166">string</span><span class="sxs-lookup"><span data-stu-id="20060-166">string</span></span> | <span data-ttu-id="20060-167">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="20060-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="20060-168">9 </span><span class="sxs-lookup"><span data-stu-id="20060-168">9</span></span>
<span data-ttu-id="20060-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="20060-169">ConfigurationName</span></span> | <span data-ttu-id="20060-170">string</span><span class="sxs-lookup"><span data-stu-id="20060-170">string</span></span> | <span data-ttu-id="20060-171">Nombre para mostrar de la configuración</span><span class="sxs-lookup"><span data-stu-id="20060-171">Display name of the configuration</span></span> | <span data-ttu-id="20060-172">Incorporar dispositivos a Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="20060-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="20060-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="20060-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="20060-174">string</span><span class="sxs-lookup"><span data-stu-id="20060-174">string</span></span> | <span data-ttu-id="20060-175">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="20060-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="20060-176">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="20060-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="20060-177">Dispositivos integrados</span><span class="sxs-lookup"><span data-stu-id="20060-177">Onboard Devices</span></span>
<span data-ttu-id="20060-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="20060-178">DeviceId</span></span> | <span data-ttu-id="20060-179">string</span><span class="sxs-lookup"><span data-stu-id="20060-179">string</span></span> | <span data-ttu-id="20060-180">Identificador único del dispositivo en el servicio.</span><span class="sxs-lookup"><span data-stu-id="20060-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="20060-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="20060-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="20060-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="20060-182">DeviceName</span></span> | <span data-ttu-id="20060-183">string</span><span class="sxs-lookup"><span data-stu-id="20060-183">string</span></span> | <span data-ttu-id="20060-184">Nombre de dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20060-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="20060-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20060-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="20060-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="20060-186">IsApplicable</span></span> | <span data-ttu-id="20060-187">bool</span><span class="sxs-lookup"><span data-stu-id="20060-187">bool</span></span> | <span data-ttu-id="20060-188">Indica si la configuración o directiva es aplicable</span><span class="sxs-lookup"><span data-stu-id="20060-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="20060-189">true</span><span class="sxs-lookup"><span data-stu-id="20060-189">true</span></span>
<span data-ttu-id="20060-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="20060-190">IsCompliant</span></span> | <span data-ttu-id="20060-191">bool</span><span class="sxs-lookup"><span data-stu-id="20060-191">bool</span></span> | <span data-ttu-id="20060-192">Indica si la configuración o la directiva está configurada correctamente</span><span class="sxs-lookup"><span data-stu-id="20060-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="20060-193">false</span><span class="sxs-lookup"><span data-stu-id="20060-193">false</span></span>
<span data-ttu-id="20060-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="20060-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="20060-195">bool</span><span class="sxs-lookup"><span data-stu-id="20060-195">bool</span></span> | <span data-ttu-id="20060-196">Indica si habrá impacto del usuario si se aplicará la configuración</span><span class="sxs-lookup"><span data-stu-id="20060-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="20060-197">true</span><span class="sxs-lookup"><span data-stu-id="20060-197">true</span></span>
<span data-ttu-id="20060-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="20060-198">OSPlatform</span></span> | <span data-ttu-id="20060-199">string</span><span class="sxs-lookup"><span data-stu-id="20060-199">string</span></span> | <span data-ttu-id="20060-200">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20060-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="20060-201">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="20060-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="20060-202">Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="20060-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="20060-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="20060-203">Windows10</span></span>
<span data-ttu-id="20060-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="20060-204">RbacGroupName</span></span> | <span data-ttu-id="20060-205">string</span><span class="sxs-lookup"><span data-stu-id="20060-205">string</span></span> | <span data-ttu-id="20060-206">Grupo de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="20060-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="20060-207">Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="20060-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="20060-208">Si la organización no contiene ningún grupo RBAC, el valor será "None".</span><span class="sxs-lookup"><span data-stu-id="20060-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="20060-209">Servidores</span><span class="sxs-lookup"><span data-stu-id="20060-209">Servers</span></span>
<span data-ttu-id="20060-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="20060-210">RecommendationReference</span></span> | <span data-ttu-id="20060-211">string</span><span class="sxs-lookup"><span data-stu-id="20060-211">string</span></span> | <span data-ttu-id="20060-212">Una referencia al identificador de recomendación relacionado con este software.</span><span class="sxs-lookup"><span data-stu-id="20060-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="20060-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="20060-213">sca-_-scid-20000</span></span>
<span data-ttu-id="20060-214">Timestamp</span><span class="sxs-lookup"><span data-stu-id="20060-214">Timestamp</span></span> | <span data-ttu-id="20060-215">string</span><span class="sxs-lookup"><span data-stu-id="20060-215">string</span></span> | <span data-ttu-id="20060-216">La última vez que se vio la configuración en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="20060-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="20060-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="20060-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="20060-218">1.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="20060-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="20060-219">1.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="20060-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="20060-220">Ejemplo de respuesta 1.6.2</span><span class="sxs-lookup"><span data-stu-id="20060-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="20060-221">2. Exportar evaluación de configuración segura (a través de archivos)</span><span class="sxs-lookup"><span data-stu-id="20060-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="20060-222">Descripción del método api 2.1</span><span class="sxs-lookup"><span data-stu-id="20060-222">2.1 API method description</span></span>

<span data-ttu-id="20060-223">Esta respuesta de la API contiene la evaluación de configuración segura en los dispositivos expuestos y devuelve una entrada para cada combinación única de DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="20060-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="20060-224">2.1.2 Limitaciones</span><span class="sxs-lookup"><span data-stu-id="20060-224">2.1.2 Limitations</span></span>

<span data-ttu-id="20060-225">Las limitaciones de velocidad para esta API son 5 llamadas por minuto y 20 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="20060-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="20060-226">2.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="20060-226">2.2 Permissions</span></span>

<span data-ttu-id="20060-227">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="20060-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="20060-228">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="20060-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="20060-229">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="20060-229">Permission type</span></span> | <span data-ttu-id="20060-230">Permiso</span><span class="sxs-lookup"><span data-stu-id="20060-230">Permission</span></span> | <span data-ttu-id="20060-231">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="20060-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="20060-232">Aplicación</span><span class="sxs-lookup"><span data-stu-id="20060-232">Application</span></span> | <span data-ttu-id="20060-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="20060-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="20060-234">\'Leer la información Administración de amenazas y vulnerabilidades vulnerabilidad de "Administración de amenazas y vulnerabilidades"\'</span><span class="sxs-lookup"><span data-stu-id="20060-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="20060-235">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="20060-235">Delegated (work or school account)</span></span> | <span data-ttu-id="20060-236">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="20060-236">Vulnerability.Read</span></span> | <span data-ttu-id="20060-237">\'Leer la información Administración de amenazas y vulnerabilidades vulnerabilidad de "Administración de amenazas y vulnerabilidades"\'</span><span class="sxs-lookup"><span data-stu-id="20060-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="20060-238">DIRECCIÓN URL 2.3</span><span class="sxs-lookup"><span data-stu-id="20060-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="20060-239">Parameters</span><span class="sxs-lookup"><span data-stu-id="20060-239">Parameters</span></span>

- <span data-ttu-id="20060-240">sasValidHours: el número de horas durante las que las direcciones URL de descarga serán válidas (máximo 24 horas).</span><span class="sxs-lookup"><span data-stu-id="20060-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="20060-241">2.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="20060-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="20060-242">Los archivos son archivos comprimidos de gzip & en formato Json de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="20060-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="20060-243">Las direcciones URL de descarga solo son válidas durante 3 horas; de lo contrario, puede usar el parámetro.</span><span class="sxs-lookup"><span data-stu-id="20060-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="20060-244">Para obtener la velocidad máxima de descarga de los datos, puede asegurarse de que está descargando desde la misma región de Azure en la que residen los datos.</span><span class="sxs-lookup"><span data-stu-id="20060-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="20060-245">Propiedad (ID)</span><span class="sxs-lookup"><span data-stu-id="20060-245">Property (ID)</span></span> | <span data-ttu-id="20060-246">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="20060-246">Data type</span></span> | <span data-ttu-id="20060-247">Description</span><span class="sxs-lookup"><span data-stu-id="20060-247">Description</span></span> | <span data-ttu-id="20060-248">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20060-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="20060-249">Exportar archivos</span><span class="sxs-lookup"><span data-stu-id="20060-249">Export files</span></span> | <span data-ttu-id="20060-250">cadena de \[ matriz\]</span><span class="sxs-lookup"><span data-stu-id="20060-250">array\[string\]</span></span> | <span data-ttu-id="20060-251">Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización</span><span class="sxs-lookup"><span data-stu-id="20060-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="20060-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="20060-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="20060-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="20060-253">GeneratedTime</span></span> | <span data-ttu-id="20060-254">string</span><span class="sxs-lookup"><span data-stu-id="20060-254">string</span></span> | <span data-ttu-id="20060-255">Hora en que se generó la exportación.</span><span class="sxs-lookup"><span data-stu-id="20060-255">The time that the export was generated.</span></span> | <span data-ttu-id="20060-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="20060-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="20060-257">2.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="20060-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="20060-258">2.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="20060-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="20060-259">Ejemplo de respuesta 2.6.2</span><span class="sxs-lookup"><span data-stu-id="20060-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="20060-260">Vea también</span><span class="sxs-lookup"><span data-stu-id="20060-260">See also</span></span>

- [<span data-ttu-id="20060-261">Exportar métodos de evaluación y propiedades por dispositivo</span><span class="sxs-lookup"><span data-stu-id="20060-261">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="20060-262">Exportar evaluación de inventario de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="20060-262">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

- [<span data-ttu-id="20060-263">Evaluación de vulnerabilidades de software de exportación por dispositivo</span><span class="sxs-lookup"><span data-stu-id="20060-263">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="20060-264">Otros relacionados</span><span class="sxs-lookup"><span data-stu-id="20060-264">Other related</span></span>

- [<span data-ttu-id="20060-265">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="20060-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="20060-266">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="20060-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
