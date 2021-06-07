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
ms.openlocfilehash: ab33db7fb7acf1969973a7af8f80ea97ef3d378f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778370"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="26af5-104">Exportar evaluación de configuración segura por dispositivo</span><span class="sxs-lookup"><span data-stu-id="26af5-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="26af5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="26af5-105">**Applies to:**</span></span>

- [<span data-ttu-id="26af5-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="26af5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="26af5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26af5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="26af5-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="26af5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="26af5-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="26af5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="26af5-110">Devuelve todas las configuraciones y su estado, por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26af5-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="26af5-111">Hay diferentes llamadas API para obtener diferentes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="26af5-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="26af5-112">Dado que la cantidad de datos puede ser grande, hay dos formas de recuperarlos:</span><span class="sxs-lookup"><span data-stu-id="26af5-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="26af5-113">[Export secure configuration assessment **OData:**](#1-export-secure-configuration-assessment-odata)la API extrae todos los datos de la organización como respuestas Json, siguiendo el protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="26af5-113">[Export secure configuration assessment **OData**](#1-export-secure-configuration-assessment-odata):  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="26af5-114">Este método es el mejor para _organizaciones pequeñas con dispositivos de menos de 100 K._</span><span class="sxs-lookup"><span data-stu-id="26af5-114">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="26af5-115">La respuesta se pagina, por lo que puede usar el campo odata.nextLink de la respuesta \@ para obtener los siguientes resultados.</span><span class="sxs-lookup"><span data-stu-id="26af5-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="26af5-116">[Exportar la evaluación de configuración **segura a través**](#2-export-secure-configuration-assessment-via-files)de archivos: esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable.</span><span class="sxs-lookup"><span data-stu-id="26af5-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="26af5-117">Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos.</span><span class="sxs-lookup"><span data-stu-id="26af5-117">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="26af5-118">Esta API extrae todos los datos de la organización como archivos de descarga.</span><span class="sxs-lookup"><span data-stu-id="26af5-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="26af5-119">La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="26af5-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="26af5-120">Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="26af5-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="26af5-121">Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="26af5-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="26af5-122">Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.</span><span class="sxs-lookup"><span data-stu-id="26af5-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="26af5-123">Los datos recopilados (mediante _OData_ o a través de _archivos)_ son la instantánea actual del estado actual y no contienen datos históricos.</span><span class="sxs-lookup"><span data-stu-id="26af5-123">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="26af5-124">Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.</span><span class="sxs-lookup"><span data-stu-id="26af5-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="26af5-125">A menos que se indique lo \*\*\*\* contrario, todos los métodos de evaluación de exportación enumerados son exportación completa y por **_dispositivo_** (también **_denominados por dispositivo_**).</span><span class="sxs-lookup"><span data-stu-id="26af5-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-odata"></a><span data-ttu-id="26af5-126">1. Exportar evaluación de configuración segura (OData)</span><span class="sxs-lookup"><span data-stu-id="26af5-126">1. Export secure configuration assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="26af5-127">Descripción del método de api 1.1</span><span class="sxs-lookup"><span data-stu-id="26af5-127">1.1 API method description</span></span>

<span data-ttu-id="26af5-128">Esta respuesta de la API contiene la evaluación de configuración segura en los dispositivos expuestos y devuelve una entrada para cada combinación única de DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="26af5-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="26af5-129">1.1.1 Limitaciones</span><span class="sxs-lookup"><span data-stu-id="26af5-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="26af5-130">El tamaño máximo de página es 200 000.</span><span class="sxs-lookup"><span data-stu-id="26af5-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="26af5-131">Las limitaciones de velocidad para esta API son 30 llamadas por minuto y 1000 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="26af5-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="26af5-132">1.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="26af5-132">1.2 Permissions</span></span>

<span data-ttu-id="26af5-133">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="26af5-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="26af5-134">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="26af5-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="26af5-135">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="26af5-135">Permission type</span></span> | <span data-ttu-id="26af5-136">Permiso</span><span class="sxs-lookup"><span data-stu-id="26af5-136">Permission</span></span> | <span data-ttu-id="26af5-137">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="26af5-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="26af5-138">Aplicación</span><span class="sxs-lookup"><span data-stu-id="26af5-138">Application</span></span> | <span data-ttu-id="26af5-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="26af5-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="26af5-140">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="26af5-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="26af5-141">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="26af5-141">Delegated (work or school account)</span></span> | <span data-ttu-id="26af5-142">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="26af5-142">Vulnerability.Read</span></span> | <span data-ttu-id="26af5-143">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="26af5-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="26af5-144">DIRECCIÓN URL 1.3</span><span class="sxs-lookup"><span data-stu-id="26af5-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="26af5-145">1.4 Parámetros</span><span class="sxs-lookup"><span data-stu-id="26af5-145">1.4 Parameters</span></span>

- <span data-ttu-id="26af5-146">pageSize \( predeterminado = 50.000: \) número de resultados en la respuesta</span><span class="sxs-lookup"><span data-stu-id="26af5-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="26af5-147">\$top: el número de resultados que se devolverán no \( devuelve odata.nextLink y, por lo tanto, \@ no extrae todos los datos\)</span><span class="sxs-lookup"><span data-stu-id="26af5-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="26af5-148">1.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="26af5-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="26af5-149">Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="26af5-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="26af5-150">Al ejecutar esta API, el resultado resultante no se devolverá necesariamente en el mismo orden enumerado en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="26af5-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="26af5-151">Es posible que se devuelvan algunas columnas adicionales en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="26af5-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="26af5-152">Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.</span><span class="sxs-lookup"><span data-stu-id="26af5-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="26af5-153">Propiedad (ID)</span><span class="sxs-lookup"><span data-stu-id="26af5-153">Property (ID)</span></span> | <span data-ttu-id="26af5-154">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="26af5-154">Data type</span></span> | <span data-ttu-id="26af5-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="26af5-155">Description</span></span> | <span data-ttu-id="26af5-156">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="26af5-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="26af5-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="26af5-157">ConfigurationCategory</span></span> | <span data-ttu-id="26af5-158">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-158">string</span></span> | <span data-ttu-id="26af5-159">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="26af5-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="26af5-160">Controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="26af5-160">Security controls</span></span>
<span data-ttu-id="26af5-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="26af5-161">ConfigurationId</span></span> | <span data-ttu-id="26af5-162">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-162">string</span></span> | <span data-ttu-id="26af5-163">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="26af5-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="26af5-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="26af5-164">scid-10000</span></span>
<span data-ttu-id="26af5-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="26af5-165">ConfigurationImpact</span></span> | <span data-ttu-id="26af5-166">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-166">string</span></span> | <span data-ttu-id="26af5-167">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="26af5-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="26af5-168">9 </span><span class="sxs-lookup"><span data-stu-id="26af5-168">9</span></span>
<span data-ttu-id="26af5-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="26af5-169">ConfigurationName</span></span> | <span data-ttu-id="26af5-170">string</span><span class="sxs-lookup"><span data-stu-id="26af5-170">string</span></span> | <span data-ttu-id="26af5-171">Nombre para mostrar de la configuración</span><span class="sxs-lookup"><span data-stu-id="26af5-171">Display name of the configuration</span></span> | <span data-ttu-id="26af5-172">Incorporar dispositivos a Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="26af5-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="26af5-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="26af5-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="26af5-174">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-174">string</span></span> | <span data-ttu-id="26af5-175">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="26af5-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="26af5-176">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="26af5-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="26af5-177">Dispositivos integrados</span><span class="sxs-lookup"><span data-stu-id="26af5-177">Onboard Devices</span></span>
<span data-ttu-id="26af5-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="26af5-178">DeviceId</span></span> | <span data-ttu-id="26af5-179">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-179">string</span></span> | <span data-ttu-id="26af5-180">Identificador único del dispositivo en el servicio.</span><span class="sxs-lookup"><span data-stu-id="26af5-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="26af5-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="26af5-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="26af5-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="26af5-182">DeviceName</span></span> | <span data-ttu-id="26af5-183">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-183">string</span></span> | <span data-ttu-id="26af5-184">Nombre de dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26af5-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="26af5-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26af5-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="26af5-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="26af5-186">IsApplicable</span></span> | <span data-ttu-id="26af5-187">bool</span><span class="sxs-lookup"><span data-stu-id="26af5-187">bool</span></span> | <span data-ttu-id="26af5-188">Indica si la configuración o directiva es aplicable</span><span class="sxs-lookup"><span data-stu-id="26af5-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="26af5-189">true</span><span class="sxs-lookup"><span data-stu-id="26af5-189">true</span></span>
<span data-ttu-id="26af5-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="26af5-190">IsCompliant</span></span> | <span data-ttu-id="26af5-191">bool</span><span class="sxs-lookup"><span data-stu-id="26af5-191">bool</span></span> | <span data-ttu-id="26af5-192">Indica si la configuración o la directiva está configurada correctamente</span><span class="sxs-lookup"><span data-stu-id="26af5-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="26af5-193">false</span><span class="sxs-lookup"><span data-stu-id="26af5-193">false</span></span>
<span data-ttu-id="26af5-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="26af5-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="26af5-195">bool</span><span class="sxs-lookup"><span data-stu-id="26af5-195">bool</span></span> | <span data-ttu-id="26af5-196">Indica si habrá impacto del usuario si se aplicará la configuración</span><span class="sxs-lookup"><span data-stu-id="26af5-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="26af5-197">true</span><span class="sxs-lookup"><span data-stu-id="26af5-197">true</span></span>
<span data-ttu-id="26af5-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="26af5-198">OSPlatform</span></span> | <span data-ttu-id="26af5-199">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-199">string</span></span> | <span data-ttu-id="26af5-200">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26af5-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="26af5-201">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="26af5-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="26af5-202">Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="26af5-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="26af5-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="26af5-203">Windows10</span></span>
<span data-ttu-id="26af5-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="26af5-204">RbacGroupName</span></span> | <span data-ttu-id="26af5-205">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-205">string</span></span> | <span data-ttu-id="26af5-206">Grupo de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="26af5-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="26af5-207">Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="26af5-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="26af5-208">Si la organización no contiene ningún grupo RBAC, el valor será "None".</span><span class="sxs-lookup"><span data-stu-id="26af5-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="26af5-209">Servidores</span><span class="sxs-lookup"><span data-stu-id="26af5-209">Servers</span></span>
<span data-ttu-id="26af5-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="26af5-210">RecommendationReference</span></span> | <span data-ttu-id="26af5-211">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-211">string</span></span> | <span data-ttu-id="26af5-212">Una referencia al identificador de recomendación relacionado con este software.</span><span class="sxs-lookup"><span data-stu-id="26af5-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="26af5-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="26af5-213">sca-_-scid-20000</span></span>
<span data-ttu-id="26af5-214">Timestamp</span><span class="sxs-lookup"><span data-stu-id="26af5-214">Timestamp</span></span> | <span data-ttu-id="26af5-215">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-215">string</span></span> | <span data-ttu-id="26af5-216">La última vez que se vio la configuración en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="26af5-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="26af5-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="26af5-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="26af5-218">1.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="26af5-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="26af5-219">1.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="26af5-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="26af5-220">Ejemplo de respuesta 1.6.2</span><span class="sxs-lookup"><span data-stu-id="26af5-220">1.6.2 Response example</span></span>

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

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="26af5-221">2. Exportar evaluación de configuración segura (a través de archivos)</span><span class="sxs-lookup"><span data-stu-id="26af5-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="26af5-222">Descripción del método api 2.1</span><span class="sxs-lookup"><span data-stu-id="26af5-222">2.1 API method description</span></span>

<span data-ttu-id="26af5-223">Esta respuesta de la API contiene la evaluación de configuración segura en los dispositivos expuestos y devuelve una entrada para cada combinación única de DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="26af5-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="26af5-224">2.1.2 Limitaciones</span><span class="sxs-lookup"><span data-stu-id="26af5-224">2.1.2 Limitations</span></span>

<span data-ttu-id="26af5-225">Las limitaciones de velocidad para esta API son 5 llamadas por minuto y 20 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="26af5-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="26af5-226">2.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="26af5-226">2.2 Permissions</span></span>

<span data-ttu-id="26af5-227">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="26af5-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="26af5-228">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="26af5-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="26af5-229">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="26af5-229">Permission type</span></span> | <span data-ttu-id="26af5-230">Permiso</span><span class="sxs-lookup"><span data-stu-id="26af5-230">Permission</span></span> | <span data-ttu-id="26af5-231">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="26af5-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="26af5-232">Aplicación</span><span class="sxs-lookup"><span data-stu-id="26af5-232">Application</span></span> | <span data-ttu-id="26af5-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="26af5-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="26af5-234">\'Leer la información Administración de amenazas y vulnerabilidades vulnerabilidad de "Administración de amenazas y vulnerabilidades"\'</span><span class="sxs-lookup"><span data-stu-id="26af5-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="26af5-235">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="26af5-235">Delegated (work or school account)</span></span> | <span data-ttu-id="26af5-236">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="26af5-236">Vulnerability.Read</span></span> | <span data-ttu-id="26af5-237">\'Leer la información Administración de amenazas y vulnerabilidades vulnerabilidad de "Administración de amenazas y vulnerabilidades"\'</span><span class="sxs-lookup"><span data-stu-id="26af5-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="26af5-238">DIRECCIÓN URL 2.3</span><span class="sxs-lookup"><span data-stu-id="26af5-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="26af5-239">Parameters</span><span class="sxs-lookup"><span data-stu-id="26af5-239">Parameters</span></span>

- <span data-ttu-id="26af5-240">sasValidHours: el número de horas durante las que las direcciones URL de descarga serán válidas (máximo 24 horas).</span><span class="sxs-lookup"><span data-stu-id="26af5-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="26af5-241">2.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="26af5-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="26af5-242">Los archivos son archivos comprimidos de gzip & en formato Json de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="26af5-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="26af5-243">Las direcciones URL de descarga solo son válidas durante 3 horas; de lo contrario, puede usar el parámetro.</span><span class="sxs-lookup"><span data-stu-id="26af5-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="26af5-244">Para obtener la velocidad máxima de descarga de los datos, puede asegurarse de que está descargando desde la misma región de Azure en la que residen los datos.</span><span class="sxs-lookup"><span data-stu-id="26af5-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="26af5-245">Propiedad (ID)</span><span class="sxs-lookup"><span data-stu-id="26af5-245">Property (ID)</span></span> | <span data-ttu-id="26af5-246">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="26af5-246">Data type</span></span> | <span data-ttu-id="26af5-247">Descripción</span><span class="sxs-lookup"><span data-stu-id="26af5-247">Description</span></span> | <span data-ttu-id="26af5-248">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="26af5-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="26af5-249">Exportar archivos</span><span class="sxs-lookup"><span data-stu-id="26af5-249">Export files</span></span> | <span data-ttu-id="26af5-250">cadena de \[ matriz\]</span><span class="sxs-lookup"><span data-stu-id="26af5-250">array\[string\]</span></span> | <span data-ttu-id="26af5-251">Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización</span><span class="sxs-lookup"><span data-stu-id="26af5-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="26af5-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="26af5-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="26af5-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="26af5-253">GeneratedTime</span></span> | <span data-ttu-id="26af5-254">cadena</span><span class="sxs-lookup"><span data-stu-id="26af5-254">string</span></span> | <span data-ttu-id="26af5-255">Hora en que se generó la exportación.</span><span class="sxs-lookup"><span data-stu-id="26af5-255">The time that the export was generated.</span></span> | <span data-ttu-id="26af5-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="26af5-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="26af5-257">2.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="26af5-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="26af5-258">2.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="26af5-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="26af5-259">Ejemplo de respuesta 2.6.2</span><span class="sxs-lookup"><span data-stu-id="26af5-259">2.6.2 Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="26af5-260">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26af5-260">See also</span></span>

- [<span data-ttu-id="26af5-261">Exportar métodos de evaluación y propiedades por dispositivo</span><span class="sxs-lookup"><span data-stu-id="26af5-261">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="26af5-262">Exportar evaluación de inventario de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="26af5-262">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

- [<span data-ttu-id="26af5-263">Evaluación de vulnerabilidades de software de exportación por dispositivo</span><span class="sxs-lookup"><span data-stu-id="26af5-263">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="26af5-264">Otros relacionados</span><span class="sxs-lookup"><span data-stu-id="26af5-264">Other related</span></span>

- [<span data-ttu-id="26af5-265">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="26af5-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="26af5-266">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="26af5-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
