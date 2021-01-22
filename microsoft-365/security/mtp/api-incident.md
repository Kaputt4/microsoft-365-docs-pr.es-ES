---
title: API de incidentes de Microsoft 365 Defender y el tipo de recurso de incidente
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Incidente en Microsoft 365 Defender
keywords: incidente, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928359"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>API de incidentes de Microsoft 365 Defender y el tipo de recurso de incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Un [incidente es](incidents-overview.md) una colección de alertas relacionadas que ayudan a describir un ataque. Microsoft 365 Defender agrega automáticamente eventos de diferentes entidades de su organización. Puede usar la API de incidentes para acceder mediante programación a los incidentes de su organización y a las alertas relacionadas.

## <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora. Cada método también tiene sus propias cuotas. Para obtener más información sobre las cuotas específicas del método, consulta el artículo correspondiente sobre el método que quieres usar.

Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado. El cuerpo de la respuesta incluirá el tiempo hasta que se restablezca la cuota alcanzada.

## <a name="permissions"></a>Permisos

La API de incidentes requiere diferentes tipos de permisos para cada uno de sus métodos. Para obtener más información acerca de los permisos necesarios, vea el artículo del método respectivo.

## <a name="methods"></a>Methods

Método | Tipo de valor devuelto | Descripción
-|-|-
[Lista de Incidentes](api-list-incidents.md) | [Lista de](api-incident.md) incidentes | Obtener una lista de incidentes.
[Incidente de actualización](api-update-incidents.md) | [Incidente](api-incident.md) | Actualizar un incidente específico.

## <a name="request-body-response-and-examples"></a>Cuerpo de la solicitud, respuesta y ejemplos

Consulte los artículos de métodos respectivos para obtener más información sobre cómo construir una solicitud o analizar una respuesta, y para obtener ejemplos prácticos.

## <a name="common-properties"></a>Propiedades comunes

Propiedad | Tipo | Descripción
-|-|-
incidentId | largo | Identificador único del incidente.
redirectIncidentId | long que admite valores NULL | El identificador de incidente con el que se ha combinado el incidente actual.
incidentName | string | Nombre del incidente.
createdTime | DateTimeOffset | Fecha y hora (en UTC) en que se creó el incidente.
lastUpdateTime | DateTimeOffset | Fecha y hora (en UTC) en que se actualizó por última vez el incidente.
assignedTo | string | Propietario del incidente.
severity | Enum | Gravedad del incidente. Los valores posibles ```UnSpecified``` son: ```Informational``` , , y ```Low``` ```Medium``` ```High``` .
status | Enum | Especifica el estado actual del incidente. Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .
classification | Enum | Especificación del incidente. Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.
determinación | Enum | Especifica la determinación del incidente. Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | lista de cadenas | Lista de etiquetas de incidentes.
alerts | Lista de alertas | Lista de alertas relacionadas. Vea ejemplos en la [documentación de la](api-list-incidents.md) API de incidentes de lista.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Información general sobre incidentes](incidents-overview.md)
- [Enumerar la API de incidentes](api-list-incidents.md)
- [ACTUALIZAR API de incidentes](api-update-incidents.md)
