---
title: Tipo de recurso Investigación
description: Entidad de Microsoft Defender para Endpoint Investigation.
keywords: apis, api de gráficos, api admitidas, get, alerts, investigations
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 54e060f1cc98f62ca048ce8d561247c47f189f24
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218390"
---
# <a name="investigation-resource-type"></a>Tipo de recurso Investigación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Representa una entidad de investigación automatizada en Defender para endpoint.

Vea [Overview of automated investigations](automated-investigations.md) para obtener más información.

## <a name="methods"></a>Métodos

Método|Tipo de valor devuelto|Description
:---|:---|:---
[Enumerar investigaciones](get-investigation-collection.md)|Colección Investigation|Obtener colección de investigación
[Obtener una sola investigación](get-investigation-object.md)|Entidad de investigación|Obtiene una sola entidad Investigation.
[Iniciar investigación](initiate-autoir-investigation.md)|Entidad de investigación|Inicia Investigación en un dispositivo.

## <a name="properties"></a>Propiedades

Propiedad|Tipo|Descripción
:---|:---|:---
id|Cadena|Identidad de la entidad de investigación. 
startTime|DateTime Nullable|La fecha y hora en que se creó la investigación.
endTime|DateTime Nullable|La fecha y la hora en que se completó la investigación.
cancelledBy|Cadena|El identificador del usuario o aplicación que canceló esa investigación.
state|Enum|El estado actual de la investigación. Los valores posibles son: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
statusDetails|Cadena|Información adicional sobre el estado de la investigación.
machineId|Cadena|El identificador del dispositivo en el que se ejecuta la investigación.
computerDnsName|Cadena|Nombre del dispositivo en el que se ejecuta la investigación.
triggeringAlertId|Cadena|El identificador de la alerta que desencadenó la investigación.

## <a name="json-representation"></a>Representación json

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
