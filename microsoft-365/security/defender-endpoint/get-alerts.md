---
title: API de listas de alertas
description: Obtenga información sobre cómo usar la API de alertas de lista para recuperar una colección de alertas en Microsoft Defender para endpoint.
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
ms.openlocfilehash: f4b62ca7fecb8e66fc082b6cf0972c1c2c06afb5
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166976"
---
# <a name="list-alerts-api"></a><span data-ttu-id="4a79f-104">API de listas de alertas</span><span class="sxs-lookup"><span data-stu-id="4a79f-104">List alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4a79f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4a79f-105">**Applies to:**</span></span>
- [<span data-ttu-id="4a79f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4a79f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4a79f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a79f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4a79f-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="4a79f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4a79f-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="4a79f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4a79f-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="4a79f-110">API description</span></span>
<span data-ttu-id="4a79f-111">Recupera una colección de alertas.</span><span class="sxs-lookup"><span data-stu-id="4a79f-111">Retrieves a collection of Alerts.</span></span>
<br><span data-ttu-id="4a79f-112">Admite [consultas de OData V4](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="4a79f-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="4a79f-113">Operadores compatibles con OData:</span><span class="sxs-lookup"><span data-stu-id="4a79f-113">OData supported operators:</span></span>
<br><span data-ttu-id="4a79f-114">```$filter``` on: ```alertCreationTime``` , , , , y ```lastUpdateTime``` ```incidentId``` ```InvestigationId``` ```status``` ```severity``` ```category``` properties.</span><span class="sxs-lookup"><span data-stu-id="4a79f-114">```$filter``` on: ```alertCreationTime```, ```lastUpdateTime```, ```incidentId```,```InvestigationId```, ```status```, ```severity``` and ```category``` properties.</span></span>
<br><span data-ttu-id="4a79f-115">```$top``` con un valor máximo de 10 000</span><span class="sxs-lookup"><span data-stu-id="4a79f-115">```$top``` with max value of 10,000</span></span>
<br>```$skip```
<br><span data-ttu-id="4a79f-116">```$expand``` de ```evidence```</span><span class="sxs-lookup"><span data-stu-id="4a79f-116">```$expand``` of ```evidence```</span></span>
<br><span data-ttu-id="4a79f-117">Vea ejemplos en [consultas de OData con Microsoft Defender para endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="4a79f-117">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="4a79f-118">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="4a79f-118">Limitations</span></span>
1. <span data-ttu-id="4a79f-119">Puede obtener las alertas por última vez actualizadas según el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="4a79f-119">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="4a79f-120">El tamaño máximo de página es 10.000.</span><span class="sxs-lookup"><span data-stu-id="4a79f-120">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="4a79f-121">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="4a79f-121">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="4a79f-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="4a79f-122">Permissions</span></span>
<span data-ttu-id="4a79f-123">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="4a79f-123">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4a79f-124">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4a79f-124">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4a79f-125">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="4a79f-125">Permission type</span></span> |   <span data-ttu-id="4a79f-126">Permiso</span><span class="sxs-lookup"><span data-stu-id="4a79f-126">Permission</span></span>  |   <span data-ttu-id="4a79f-127">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="4a79f-127">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4a79f-128">Aplicación</span><span class="sxs-lookup"><span data-stu-id="4a79f-128">Application</span></span> |   <span data-ttu-id="4a79f-129">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="4a79f-129">Alert.Read.All</span></span> |    <span data-ttu-id="4a79f-130">'Leer todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="4a79f-130">'Read all alerts'</span></span>
<span data-ttu-id="4a79f-131">Aplicación</span><span class="sxs-lookup"><span data-stu-id="4a79f-131">Application</span></span> |   <span data-ttu-id="4a79f-132">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4a79f-132">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="4a79f-133">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="4a79f-133">'Read and write all alerts'</span></span>
<span data-ttu-id="4a79f-134">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="4a79f-134">Delegated (work or school account)</span></span> | <span data-ttu-id="4a79f-135">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="4a79f-135">Alert.Read</span></span> | <span data-ttu-id="4a79f-136">'Leer alertas'</span><span class="sxs-lookup"><span data-stu-id="4a79f-136">'Read alerts'</span></span>
<span data-ttu-id="4a79f-137">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="4a79f-137">Delegated (work or school account)</span></span> | <span data-ttu-id="4a79f-138">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4a79f-138">Alert.ReadWrite</span></span> | <span data-ttu-id="4a79f-139">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="4a79f-139">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="4a79f-140">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="4a79f-140">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4a79f-141">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="4a79f-141">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4a79f-142">La respuesta incluirá solo alertas asociadas a dispositivos a los que el usuario pueda tener acceso, en función de la configuración del grupo de dispositivos (vea [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="4a79f-142">The response will include only alerts that are associated with devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4a79f-143">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="4a79f-143">HTTP request</span></span>
```
GET /api/alerts
```

## <a name="request-headers"></a><span data-ttu-id="4a79f-144">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="4a79f-144">Request headers</span></span>

<span data-ttu-id="4a79f-145">Nombre</span><span class="sxs-lookup"><span data-stu-id="4a79f-145">Name</span></span> | <span data-ttu-id="4a79f-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="4a79f-146">Type</span></span> | <span data-ttu-id="4a79f-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a79f-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="4a79f-148">Authorization</span><span class="sxs-lookup"><span data-stu-id="4a79f-148">Authorization</span></span> | <span data-ttu-id="4a79f-149">Cadena</span><span class="sxs-lookup"><span data-stu-id="4a79f-149">String</span></span> | <span data-ttu-id="4a79f-150">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="4a79f-150">Bearer {token}.</span></span> <span data-ttu-id="4a79f-151">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="4a79f-151">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4a79f-152">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="4a79f-152">Request body</span></span>
<span data-ttu-id="4a79f-153">En blanco</span><span class="sxs-lookup"><span data-stu-id="4a79f-153">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4a79f-154">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4a79f-154">Response</span></span>
<span data-ttu-id="4a79f-155">Si se realiza correctamente, este método devuelve 200 Ok y una lista de objetos [de alerta](alerts.md) en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="4a79f-155">If successful, this method returns 200 OK, and a list of [alert](alerts.md) objects in the response body.</span></span>


## <a name="example-1---default"></a><span data-ttu-id="4a79f-156">Ejemplo 1: valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="4a79f-156">Example 1 - Default</span></span>

<span data-ttu-id="4a79f-157">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="4a79f-157">**Request**</span></span>

<span data-ttu-id="4a79f-158">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4a79f-158">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts
```

<span data-ttu-id="4a79f-159">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="4a79f-159">**Response**</span></span>

<span data-ttu-id="4a79f-160">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="4a79f-160">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="4a79f-161">La lista de respuestas que se muestra aquí puede truncarse por brevedad.</span><span class="sxs-lookup"><span data-stu-id="4a79f-161">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="4a79f-162">Todas las alertas se devolverán de una llamada real.</span><span class="sxs-lookup"><span data-stu-id="4a79f-162">All alerts will be returned from an actual call.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637308392288907382_-880718168",
            "incidentId": 7587,
            "investigationId": 723156,
            "assignedTo": "secop123@contoso.com",
            "severity": "Low",
            "status": "New",
            "classification": "TruePositive",
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAv",
            "category": "SuspiciousActivity",
            "threatFamilyName": "Meterpreter",
            "title": "Suspicious 'Meterpreter' behavior was detected",
            "description": "Malware and unwanted software are undesirable applications that perform annoying, disruptive, or harmful actions on affected machines. Some of these undesirable applications can replicate and spread from one machine to another. Others are able to receive commands from remote attackers and perform activities associated with cyber attacks.\n\nA malware is considered active if it is found running on the machine or it already has persistence mechanisms in place. Active malware detections are assigned higher severity ratings.\n\nBecause this malware was active, take precautionary measures and check for residual signs of infection.",
            "alertCreationTime": "2020-07-20T10:53:48.7657932Z",
            "firstEventTime": "2020-07-20T10:52:17.6654369Z",
            "lastEventTime": "2020-07-20T10:52:18.1362905Z",
            "lastUpdateTime": "2020-07-20T10:53:50.19Z",
            "resolvedTime": null,
            "machineId": "12ee6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "MiddleEast",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2020-07-21T01:00:37.8404534Z"
                }
            ],
            "evidence": []
        }
        ...
    ]
}
```

## <a name="example-2---get-10-latest-alerts-with-related-evidence"></a><span data-ttu-id="4a79f-163">Ejemplo 2: Obtener 10 alertas más recientes con evidencia relacionada</span><span class="sxs-lookup"><span data-stu-id="4a79f-163">Example 2 - Get 10 latest Alerts with related Evidence</span></span>

<span data-ttu-id="4a79f-164">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="4a79f-164">**Request**</span></span>

<span data-ttu-id="4a79f-165">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4a79f-165">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts?$top=10&$expand=evidence
```


<span data-ttu-id="4a79f-166">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="4a79f-166">**Response**</span></span>

<span data-ttu-id="4a79f-167">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="4a79f-167">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="4a79f-168">La lista de respuestas que se muestra aquí puede truncarse por brevedad.</span><span class="sxs-lookup"><span data-stu-id="4a79f-168">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="4a79f-169">Todas las alertas se devolverán de una llamada real.</span><span class="sxs-lookup"><span data-stu-id="4a79f-169">All alerts will be returned from an actual call.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637472900382838869_1364969609",
            "incidentId": 1126093,
            "investigationId": null,
            "assignedTo": null,
            "severity": "Low",
            "status": "New",
            "classification": null,
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAtp",
            "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
            "category": "Execution",
            "threatFamilyName": null,
            "title": "Low-reputation arbitrary code executed by signed executable",
            "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
            "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
            "firstEventTime": "2021-01-26T20:31:32.9562661Z",
            "lastEventTime": "2021-01-26T20:31:33.0577322Z",
            "lastUpdateTime": "2021-01-26T20:33:59.2Z",
            "resolvedTime": null,
            "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "A",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "MIDDLEEAST"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "evidence": [
                {
                    "entityType": "User",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": null,
                    "sha256": null,
                    "fileName": null,
                    "filePath": null,
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": "eranb",
                    "domainName": "MIDDLEEAST",
                    "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
                    "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
                    "userPrincipalName": "temp123@microsoft.com",
                    "detectionStatus": null
                },
                {
                    "entityType": "Process",
                    "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
                    "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
                    "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
                    "fileName": "rundll32.exe",
                    "filePath": "C:\\Windows\\SysWOW64",
                    "processId": 3276,
                    "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
                    "processCreationTime": "2021-01-26T20:31:32.9581596Z",
                    "parentProcessId": 8420,
                    "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
                    "parentProcessFileName": "rundll32.exe",
                    "parentProcessFilePath": "C:\\Windows\\System32",
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                },
                {
                    "entityType": "File",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
                    "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
                    "fileName": "suspicious.dll",
                    "filePath": "c:\\temp",
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                }
            ]
        },
        ...
    ]
}
```


## <a name="see-also"></a><span data-ttu-id="4a79f-170">Ver también</span><span class="sxs-lookup"><span data-stu-id="4a79f-170">See also</span></span>
- [<span data-ttu-id="4a79f-171">Consultas de OData con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="4a79f-171">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
