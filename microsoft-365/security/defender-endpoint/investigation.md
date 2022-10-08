---
title: Tipo de recurso de investigación
description: Microsoft Defender para punto de conexión entidad De investigación.
keywords: apis, graph api, api admitidas, get, alerts, investigations
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 9b388cf1b133025a4782b5179cfb8581e83db173
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232284"
---
# <a name="investigation-resource-type"></a>Tipo de recurso de investigación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

Representa una entidad de investigación automatizada en Defender para punto de conexión.

Para obtener más información, consulte [Introducción a las investigaciones automatizadas](automated-investigations.md).

## <a name="methods"></a>Métodos

Método|Tipo de valor devuelto|Descripción
:---|:---|:---
[Enumeración de investigaciones](get-investigation-collection.md)|Colección de investigación|Obtención de la colección de investigación
[Obtener una sola investigación](get-investigation-object.md)|Entidad de investigación|Obtiene una sola entidad Investigation.
[Iniciar investigación](initiate-autoir-investigation.md)|Entidad de investigación|Inicia la investigación en un dispositivo.

## <a name="properties"></a>Propiedades

Propiedad|Tipo|Descripción
:---|:---|:---
Id.|Cadena|Identidad de la entidad de investigación. 
startTime|DateTime admite valores NULL|Fecha y hora en que se creó la investigación.
endTime|DateTime admite valores NULL|Fecha y hora en que se completó la investigación.
cancelledBy|Cadena|Identificador del usuario o aplicación que canceló esa investigación.
Estado|Enum|Estado actual de la investigación. Los valores posibles son: "Desconocido", 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
statusDetails|Cadena|Información adicional sobre el estado de la investigación.
machineId|Cadena|Identificador del dispositivo en el que se ejecuta la investigación.
computerDnsName|Cadena|Nombre del dispositivo en el que se ejecuta la investigación.
triggeringAlertId|Cadena|Identificador de la alerta que desencadenó la investigación.

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
