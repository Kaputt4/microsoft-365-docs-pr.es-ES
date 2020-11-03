---
title: Tipo de recurso Incident en la API de Microsoft 365 defender
description: Obtenga información sobre los métodos y las propiedades del tipo de recurso Incident en Microsoft 365 defender
keywords: incidente, incidentes, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844025"
---
# <a name="incident-resource-type"></a>Tipo de recurso Incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

>[!IMPORTANT] 
>Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>Métodos

Método |Tipo de valor devuelto |Description
:---|:---|:---
[Lista de Incidentes](api-list-incidents.md) | Lista de [incidentes](api-incident.md) | Obtener una lista de incidentes.
[Incidente de actualización](api-update-incidents.md) | [Incidentes](api-incident.md) | Actualizar incidente específico.


## <a name="properties"></a>Propiedades

Propiedad |    Tipo    |    Description
:---|:---|:---
incidentId | largo | IDENTIFICADOR único de incidente.
redirectIncidentId | Nullable Long | IDENTIFICADOR del incidente al que se combinó el incidente actual.
incidentName | string | Nombre del incidente.
createdTime | DateTimeOffset | La fecha y hora (en UTC) en que se creó el incidente.
lastUpdateTime | DateTimeOffset | La fecha y hora (en UTC) en que se actualizó por última vez el incidente.
assignedTo | string | Propietario del incidente.
severity | Enum | Gravedad del incidente. Los valores posibles son: ```UnSpecified``` ,, ```Informational``` ```Low``` ```Medium``` y ```High``` .
status | Enum | Especifica el estado actual del incidente. Los valores posibles son ```Active``` : ```Resolved``` y ```Redirected``` .
classification | Enum | Especificación del incidente. Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.
cálculo | Enum | Especifica la determinación del incidente. Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Lista de cadenas | Lista de etiquetas de incidente.
alerts | Lista de alertas | Lista de alertas relacionadas. Consulte los ejemplos en la documentación de la API de [incidentes de lista](api-list-incidents.md) .
