---
title: Obtención de la API de alertas
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Alert en Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, get, alerts, recent
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 301abec576f15ac83406660ca75b3f9ec3b7d389
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497925"
---
# <a name="alert-resource-type"></a>Tipo de recurso de alerta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="methods"></a>Métodos

|Método|Tipo de valor devuelto|Descripción|
|---|---|---|
|[Obtener alerta](get-alert-info-by-id.md)|[Alerta](alerts.md)|Obtener un único objeto [de alerta](alerts.md) .|
|[Listar alertas](get-alerts.md)|[Colección de alertas](alerts.md)|Enumera la colección de [alertas](alerts.md) .|
|[Update alert](update-alert.md)|[Alerta](alerts.md)|Actualice [una alerta](alerts.md) específica.|
|[Alertas de actualización por lotes](batch-update-alerts.md)||Actualice un lote de [alertas](alerts.md).|
|[Crear alerta](create-alert-by-reference.md)|[Alerta](alerts.md)|Cree una alerta basada en los datos de eventos obtenidos de [la búsqueda avanzada](run-advanced-query-api.md).|
|[Enumeración de dominios relacionados](get-alert-related-domain-info.md)|Colección de dominios|Enumera las direcciones URL asociadas a la alerta.|
|[Enumerar archivos relacionados](get-alert-related-files-info.md)|[Colección de archivos](files.md)|Enumere las entidades de [archivo](files.md) asociadas a la [alerta](alerts.md).|
|[Enumerar direcciones IP relacionadas](get-alert-related-ip-info.md)|Colección ip|Enumera las direcciones IP asociadas a la alerta.|
|[Obtener máquinas relacionadas](get-alert-related-machine-info.md)|[Máquina](machine.md)|La [máquina](machine.md) asociada a la [alerta](alerts.md).|
|[Obtener usuarios relacionados](get-alert-related-user-info.md)|[Usuario](user.md)|El [usuario](user.md) que está asociado a la [alerta](alerts.md).|

## <a name="properties"></a>Propiedades

|Propiedad|Tipo|Descripción|
|---|---|---|
|id|Cadena|Identificador de alerta.|
|title|String|Título de la alerta.|
|description|String|Descripción de la alerta.|
|alertCreationTime|DateTimeOffset que admite valores NULL|Fecha y hora (en UTC) en la que se creó la alerta.|
|lastEventTime|DateTimeOffset que admite valores NULL|La última aparición del evento que desencadenó la alerta en el mismo dispositivo.|
|firstEventTime|DateTimeOffset que admite valores NULL|La primera aparición del evento que desencadenó la alerta en ese dispositivo.|
|lastUpdateTime|DateTimeOffset que admite valores NULL|Fecha y hora (en UTC) que la alerta se actualizó por última vez.|
|resolvedTime|DateTimeOffset que admite valores NULL|Fecha y hora en que se cambió el estado de la alerta a "Resuelto".|
|incidentId|Long que acepta valores NULL|Identificador [de incidente](view-incidents-queue.md) de la alerta.|
|investigationId|Long que acepta valores NULL|Identificador [de investigación](automated-investigations.md) relacionado con la alerta.|
|investigationState|Enumeración que acepta valores NULL|Estado actual de la [investigación](automated-investigations.md). Los valores posibles son: "Desconocido", 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.|
|assignedTo|Cadena|Propietario de la alerta.|
|rbacGroupName|Cadena|Nombre del grupo de dispositivos RBAC.|
|mitreTechniques|Cadena|Identificador de técnica de Mitre Enterprise.|
|relatedUser|Cadena|Detalles del usuario relacionados con una alerta específica.|
|severity|Enum|Gravedad de la alerta. Los valores posibles son: "UnSpecified", "Informational", "Low", "Medium" y "High".|
|status|Enum|Especifica el estado actual de la alerta. Los valores posibles son: "Unknown", "New", "InProgress" y "Resolved".|
|classification|Enumeración que acepta valores NULL|Especificación de la alerta. Los valores posibles son: "Unknown", "FalsePositive", "TruePositive".|
|Determinación|Enumeración que acepta valores NULL|Especifica la determinación de la alerta. Los valores posibles son: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other".|
|categoría|Cadena|Categoría de la alerta.|
|detectionSource|Cadena|Origen de detección.|
|threatFamilyName|Cadena|Familia de amenazas.|
|threatName|Cadena|Nombre de la amenaza.|
|machineId|Cadena|Identificador de una entidad de [máquina](machine.md) asociada a la alerta.|
|computerDnsName|Cadena|nombre completo de [la máquina](machine.md).|
|aadTenantId|Cadena|Identificador de Azure Active Directory.|
|detectorId|Cadena|Identificador del detector que desencadenó la alerta.|
|comments|Lista de comentarios de alerta|El objeto Alert Comment contiene: cadena de comentario, cadena createdBy y fecha y hora de createTime.|
|Evidencia|Lista de pruebas de alerta|Evidencia relacionada con la alerta. Vea el ejemplo abajo.|

>[!NOTE]
>Alrededor del 29 de agosto de 2022, los valores de determinación de alertas admitidos anteriormente ("Apt" y "SecurityPersonnel") quedarán en desuso y ya no estarán disponibles a través de la API.

### <a name="response-example-for-getting-single-alert"></a>Ejemplo de respuesta para obtener una única alerta:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
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
        "domainName": "DOMAIN"
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
            "accountName": "name",
            "domainName": "DOMAIN",
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
}
```
