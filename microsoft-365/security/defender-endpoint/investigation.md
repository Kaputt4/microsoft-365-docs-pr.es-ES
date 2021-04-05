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
ms.technology: mde
ms.openlocfilehash: 3872976717a5b472ab8d471db7eff9975dbc2258
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587688"
---
# <a name="investigation-resource-type"></a>Tipo de recurso Investigación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Representa una entidad de investigación automatizada en Defender para endpoint.
<br> Vea [Overview of automated investigations](automated-investigations.md) para obtener más información.

## <a name="methods"></a>Métodos
Método|Tipo de valor devuelto |Descripción
:---|:---|:---
[Enumerar investigaciones](get-investigation-collection.md) | Colección Investigation | Obtener colección de investigación
[Obtener una sola investigación](get-investigation-object.md) | Entidad de investigación | Obtiene una sola entidad Investigation.
[Iniciar investigación](initiate-autoir-investigation.md) | Entidad de investigación | Inicia Investigación en un dispositivo.


## <a name="properties"></a>Propiedades
Propiedad |  Tipo    |   Descripción
:---|:---|:---
id | String | Identidad de la entidad de investigación. 
startTime | DateTime Nullable | La fecha y hora en que se creó la investigación. 
endTime | DateTime Nullable | La fecha y la hora en que se completó la investigación. 
cancelledBy | String | El identificador del usuario o aplicación que canceló esa investigación. 
investigationState | Enum | El estado actual de la investigación. Los valores posibles son: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
statusDetails | String | Información adicional sobre el estado de la investigación.
machineId | String | El identificador del dispositivo en el que se ejecuta la investigación.
computerDnsName | String | Nombre del dispositivo en el que se ejecuta la investigación.
triggeringAlertId | String | El identificador de la alerta que desencadenó la investigación.


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
