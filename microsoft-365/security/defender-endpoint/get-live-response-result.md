---
title: Obtener resultados de respuesta en directo
description: Obtenga información sobre cómo recuperar un resultado de comando de respuesta en directo específico por su índice.
keywords: apis, api de gráficos, api admitidas, carga en biblioteca
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879786"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="85619-104">Obtener resultados de respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="85619-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="85619-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="85619-105">**Applies to:**</span></span>
- [<span data-ttu-id="85619-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="85619-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="85619-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="85619-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="85619-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="85619-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="85619-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="85619-109">API description</span></span>

<span data-ttu-id="85619-110">Recupera un resultado de comando de respuesta en directo específico por su índice.</span><span class="sxs-lookup"><span data-stu-id="85619-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="85619-111">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="85619-111">Limitations</span></span>

1.  <span data-ttu-id="85619-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="85619-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="85619-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="85619-113">Permissions</span></span>

<span data-ttu-id="85619-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="85619-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="85619-115">Para obtener más información, incluido cómo elegir permisos, vea [Get started](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="85619-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="85619-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="85619-116">Permission type</span></span>                    | <span data-ttu-id="85619-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="85619-117">Permission</span></span>           | <span data-ttu-id="85619-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="85619-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="85619-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="85619-119">Application</span></span>                        | <span data-ttu-id="85619-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="85619-120">Machine.LiveResponse</span></span> | <span data-ttu-id="85619-121">Ejecutar respuesta en directo en un equipo específico</span><span class="sxs-lookup"><span data-stu-id="85619-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="85619-122">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="85619-122">Delegated (work or school account)</span></span> | <span data-ttu-id="85619-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="85619-123">Machine.LiveResponse</span></span> | <span data-ttu-id="85619-124">Ejecutar respuesta en directo en un equipo específico</span><span class="sxs-lookup"><span data-stu-id="85619-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="85619-125">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="85619-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="85619-126">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="85619-126">Request headers</span></span>

| <span data-ttu-id="85619-127">Nombre</span><span class="sxs-lookup"><span data-stu-id="85619-127">Name</span></span>      | <span data-ttu-id="85619-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="85619-128">Type</span></span> | <span data-ttu-id="85619-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="85619-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="85619-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="85619-130">Authorization</span></span> | <span data-ttu-id="85619-131">Cadena</span><span class="sxs-lookup"><span data-stu-id="85619-131">String</span></span>   | <span data-ttu-id="85619-p103">{token} de portador. Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="85619-p103">Bearer {token}. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="85619-134">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="85619-134">Request body</span></span>

<span data-ttu-id="85619-135">En blanco</span><span class="sxs-lookup"><span data-stu-id="85619-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="85619-136">Respuesta</span><span class="sxs-lookup"><span data-stu-id="85619-136">Response</span></span>

<span data-ttu-id="85619-137">Si se realiza correctamente, este método devuelve 200, Ok código de respuesta con el objeto que contiene el vínculo al resultado del comando en la *propiedad value.*</span><span class="sxs-lookup"><span data-stu-id="85619-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="85619-138">Este vínculo es válido durante 30 minutos y debe usarse inmediatamente para descargar el paquete en un almacenamiento local.</span><span class="sxs-lookup"><span data-stu-id="85619-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="85619-139">Otra llamada puede volver a crear un vínculo expirado y no es necesario volver a ejecutar la respuesta en directo.</span><span class="sxs-lookup"><span data-stu-id="85619-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="85619-140">*Propiedades de transcripción de Runscript:*</span><span class="sxs-lookup"><span data-stu-id="85619-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="85619-141">Propiedad</span><span class="sxs-lookup"><span data-stu-id="85619-141">Property</span></span>  | <span data-ttu-id="85619-142">Description</span><span class="sxs-lookup"><span data-stu-id="85619-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="85619-143">name</span><span class="sxs-lookup"><span data-stu-id="85619-143">name</span></span>          | <span data-ttu-id="85619-144">Nombre de script ejecutado</span><span class="sxs-lookup"><span data-stu-id="85619-144">Executed script name</span></span>                  |
| <span data-ttu-id="85619-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="85619-145">exit_code</span></span>     | <span data-ttu-id="85619-146">Código de salida de script ejecutado</span><span class="sxs-lookup"><span data-stu-id="85619-146">Executed script exit code</span></span>             |
| <span data-ttu-id="85619-147">script_output</span><span class="sxs-lookup"><span data-stu-id="85619-147">script_output</span></span> | <span data-ttu-id="85619-148">Salida estándar de script ejecutada</span><span class="sxs-lookup"><span data-stu-id="85619-148">Executed script standard output</span></span>       |
| <span data-ttu-id="85619-149">script_error</span><span class="sxs-lookup"><span data-stu-id="85619-149">script_error</span></span>  | <span data-ttu-id="85619-150">Salida de error estándar de script ejecutada</span><span class="sxs-lookup"><span data-stu-id="85619-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="85619-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85619-151">Example</span></span>

<span data-ttu-id="85619-152">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="85619-152">**Request**</span></span>

<span data-ttu-id="85619-153">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="85619-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="85619-154">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="85619-154">**Response**</span></span>

<span data-ttu-id="85619-155">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="85619-155">Here is an example of the response.</span></span>

<span data-ttu-id="85619-156">HTTP/1.1 200 Ok</span><span class="sxs-lookup"><span data-stu-id="85619-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="85619-157">Tipo de contenido: application/json</span><span class="sxs-lookup"><span data-stu-id="85619-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="85619-158">*Contenido del archivo:*</span><span class="sxs-lookup"><span data-stu-id="85619-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="85619-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="85619-159">Related topics</span></span>

- [<span data-ttu-id="85619-160">Obtener API de acción de máquina</span><span class="sxs-lookup"><span data-stu-id="85619-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="85619-161">Cancelar la acción del equipo</span><span class="sxs-lookup"><span data-stu-id="85619-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="85619-162">Ejecutar respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="85619-162">Run live response</span></span>](run-live-response.md) 
