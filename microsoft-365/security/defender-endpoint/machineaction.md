---
title: tipo de recurso machineAction
description: Obtenga información sobre los métodos y propiedades del tipo de recurso MachineAction en Microsoft Defender para endpoint.
keywords: apis, api admitidas, get, machineaction, recent
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
ms.openlocfilehash: 33df420b8b480b6957e2ec71b3bb5494f61fce63
ms.sourcegitcommit: 7be84e7940c63b4c958b9da875d323bead9aae95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2021
ms.locfileid: "59453621"
---
# <a name="machineaction-resource-type"></a>Tipo de recurso MachineAction

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Para obtener más información, vea [Response Actions](respond-machine-alerts.md).

|Método|Tipo de valor devuelto|Descripción|
|---|---|---|
|[Enumerar MachineActions](get-machineactions-collection.md)|[Acción de máquina](machineaction.md)|Enumerar [entidades de acción](machineaction.md) de máquina.|
|[Obtener MachineAction](get-machineaction-object.md)|[Acción de máquina](machineaction.md)|Obtener una sola [entidad De acción de](machineaction.md) máquina.|
|[Recopilar paquete de investigación](collect-investigation-package.md)|[Acción de máquina](machineaction.md)|Recopilar el paquete de investigación de una [máquina](machine.md).|
|[Obtener identificador URI de SAS de paquete de investigación](get-package-sas-uri.md)|[Acción de máquina](machineaction.md)|Obtener URI para descargar el paquete de investigación.|
|[Aislar máquina](isolate-machine.md)|[Acción de máquina](machineaction.md)|[Aísle el equipo](machine.md) de la red.|
|[Liberar máquina del aislamiento](unisolate-machine.md)|[Acción de máquina](machineaction.md)|Libere [el equipo](machine.md) de Aislamiento.|
|[Restringir ejecución de aplicación](restrict-code-execution.md)|[Acción de máquina](machineaction.md)|Restringir la ejecución de la aplicación.|
|[Quitar restricción de aplicación](unrestrict-code-execution.md)|[Acción de máquina](machineaction.md)|Quitar la restricción de ejecución de aplicaciones.|
|[Ejecutar examen antivirus](run-av-scan.md)|[Acción de máquina](machineaction.md)|Ejecute un examen antivirus con Windows Defender (cuando corresponda).|
|[Retirar máquina](offboard-machine-api.md)|[Acción de máquina](machineaction.md)|Equipo fuera [de la máquina](machine.md) de Microsoft Defender para endpoint.|
|[Detener y poner en cuarentena un archivo](stop-and-quarantine-file.md)|[Acción de máquina](machineaction.md)|Detenga la ejecución de un archivo en un equipo y elimínelo.|
|[Ejecutar respuesta directa](run-live-response.md)|[Acción de máquina](machineaction.md)|Ejecuta una secuencia de comandos de respuesta en directo en un dispositivo|
|[Obtener resultado de respuesta en directo](get-live-response-result.md)|Entidad URL|Recupera el vínculo de descarga de resultados del comando de respuesta en directo específico por su índice.|
|[Cancelar acción de máquina](cancel-machine-action.md)|[Acción de máquina](machineaction.md)|Cancelar una acción de máquina activa.|

<br>

## <a name="properties"></a>Propiedades

|Propiedad|Tipo|Descripción|
|---|---|---|
|Id.|Guid|Identidad de la [entidad Acción de](machineaction.md) máquina.|
|type|Enum|Tipo de la acción. Los valores posibles son: "RunAntiVirusScan", "Offboard", "Live Response", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" y "UnrestrictCodeExecution".|
|scope|cadena|Ámbito de la acción. "Completo" o "Selectivo" para aislamiento, "Rápido" o "Completo" para el examen antivirus.|
|solicitante|Cadena|Identidad de la persona que ejecutó la acción.|
|externalID|Cadena|Id que el cliente puede enviar en la solicitud de correlación personalizada.|
|requestSource|cadena|Nombre del usuario o aplicación que envió la acción.|
|Comandos |matriz|Comandos que se ejecutarán. Los valores permitidos son PutFile, RunScript, GetFile.|
|cancellationRequestor|Cadena|Identidad de la persona que canceló la acción.|
|requestorComment|Cadena|Comentario que se escribió al emitir la acción.|
|cancellationComment|Cadena|Comentario que se escribió al cancelar la acción.|
|status|Enum|Estado actual del comando. Los valores posibles son: "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" y "Cancelled".|
|machineId|Cadena|Id. de [la máquina](machine.md) en la que se ejecutó la acción.|
|computerDnsName|Cadena|Nombre de la [máquina](machine.md) en la que se ejecutó la acción.|
|creationDateTimeUtc|DateTimeOffset|Fecha y hora en que se creó la acción.|
|cancellationDateTimeUtc|DateTimeOffset|Fecha y hora en que se canceló la acción.|
|lastUpdateDateTimeUtc|DateTimeOffset|La última fecha y hora en que se actualizó el estado de la acción.|
|title|Cadena|Título de acción de máquina.|
|relatedFileInfo|Clase|Contiene dos propiedades. string `fileIdentifier` , `fileIdentifierType` Enumerar con los valores posibles: "Sha1", "Sha256" y "Md5".|

## <a name="json-representation"></a>Representación json

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
