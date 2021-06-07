---
title: OBTENER API de alertas
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Alert en Microsoft Defender para endpoint.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c935df1abddc3d0ebee74e09280d6e3ec961ca97
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769814"
---
# <a name="alert-resource-type"></a>Tipo de recurso Alert

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Métodos

Método |Tipo de valor devuelto |Descripción
:---|:---|:---
[Obtener alerta](get-alert-info-by-id.md) | [Alerta](alerts.md) | Obtener un único [objeto de](alerts.md) alerta.
[Listar alertas](get-alerts.md) | [Colección Alert](alerts.md) | Enumerar [la colección de](alerts.md) alertas.
[Update alert](update-alert.md) | [Alerta](alerts.md) | Actualizar alerta [específica](alerts.md).
[Alertas de actualización por lotes](batch-update-alerts.md) | | Actualizar un lote de [alertas](alerts.md).
[Crear alerta](create-alert-by-reference.md)|[Alerta](alerts.md)|Crear una alerta basada en los datos de eventos obtenidos de [la búsqueda avanzada](run-advanced-query-api.md).
[Enumerar dominios relacionados](get-alert-related-domain-info.md)|Colección domain| Enumerar las direcciones URL asociadas con la alerta.
[Enumerar archivos relacionados](get-alert-related-files-info.md) | [Colección de](files.md) archivos |  Enumerar [las entidades](files.md) de archivo asociadas a la [alerta](alerts.md).
[Enumerar direcciones IP relacionadas](get-alert-related-ip-info.md) | Colección IP | Enumerar direcciones IP asociadas a la alerta.
[Obtener máquinas relacionadas](get-alert-related-machine-info.md) | [Máquina](machine.md) | El [equipo](machine.md) asociado a la [alerta](alerts.md).
[Obtener usuarios relacionados](get-alert-related-user-info.md) | [Usuario](user.md) | El [usuario](user.md) asociado a la [alerta](alerts.md).


## <a name="properties"></a>Propiedades

Propiedad |    Tipo    |    Descripción
:---|:---|:---
id | Cadena | Id. de alerta.
title | String | Título de la alerta.
description | String | Descripción de la alerta.
alertCreationTime | DateTimeOffset que admite valores NULL | La fecha y hora (en UTC) se creó la alerta.
lastEventTime | DateTimeOffset que admite valores NULL | La última aparición del evento que desencadenó la alerta en el mismo dispositivo.
firstEventTime | DateTimeOffset que admite valores NULL | La primera aparición del evento que desencadenó la alerta en ese dispositivo.
lastUpdateTime | DateTimeOffset que admite valores NULL | La fecha y hora (en UTC) la alerta se actualizó por última vez.
resolvedTime | DateTimeOffset que admite valores NULL | La fecha y hora en que se cambió el estado de la alerta a "Resuelto".
incidentId | Long que admite valores NULL | El [identificador de](view-incidents-queue.md) incidente de la alerta.
investigationId | Long que admite valores NULL | El [identificador de](automated-investigations.md) investigación relacionado con la alerta.
investigationState | Enumeración que admite valores null | El estado actual de la [investigación](automated-investigations.md). Los valores posibles son: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
assignedTo | Cadena | Propietario de la alerta.
severity | Enum | Gravedad de la alerta. Los valores posibles son: 'UnSpecified', 'Informational', 'Low', 'Medium' y 'High'.
status | Enum | Especifica el estado actual de la alerta. Los valores posibles son: "Desconocido", "Nuevo", "InProgress" y "Resuelto".
classification | Enumeración que admite valores null | Especificación de la alerta. Los valores posibles son: 'Unknown', 'FalsePositive', 'TruePositive'.
determinación | Enumeración que admite valores null | Especifica la determinación de la alerta. Los valores posibles son: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.
categoría| Cadena | Categoría de la alerta.
detectionSource | Cadena | Origen de detección.
threatFamilyName | Cadena | Familia de amenazas.
threatName | Cadena | Nombre de la amenaza.
machineId | Cadena | Id. de una [entidad de](machine.md) máquina asociada a la alerta.
computerDnsName | Cadena | [nombre](machine.md) completo de la máquina.
aadTenantId | Cadena | El Azure Active Directory de usuario.
detectorId | Cadena | El identificador del detector que desencadenó la alerta.
comments | Lista de comentarios de alerta | El objeto Alert Comment contiene: cadena de comentario, createdBy string y createTime date time.
Evidencia | Lista de pruebas de alerta | Evidencia relacionada con la alerta. Vea el ejemplo abajo.

### <a name="response-example-for-getting-single-alert"></a>Ejemplo de respuesta para obtener una sola alerta:

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
}
```
