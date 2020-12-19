---
title: API de incidentes de Microsoft 365 defender y el tipo de recurso Incident
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719339"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>API de incidentes de Microsoft 365 defender y el tipo de recurso Incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Un [incidente](incidents-overview.md) es una colección de alertas relacionadas que ayudan a describir un ataque. Microsoft 365 defender agrega automáticamente eventos de diferentes entidades de la organización. Puede usar la API de incidentes para acceder mediante programación a los incidentes de su organización y las alertas relacionadas.

## <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora. Cada método también tiene sus propias cuotas. Para obtener más información acerca de las cuotas específicas para métodos, vea el artículo correspondiente del método que desee usar.

Un `429` código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por el número de solicitudes enviadas o por el tiempo de ejecución asignado. El cuerpo de la respuesta incluirá el tiempo hasta que se restablezca la cuota que ha alcanzado.

## <a name="permissions"></a>Permisos

La API de incidentes requiere tipos de permisos diferentes para cada uno de sus métodos. Para obtener más información acerca de los permisos necesarios, vea el artículo correspondiente del método.

## <a name="methods"></a>Métodos

Método | Tipo de valor devuelto | Descripción
-|-|-
[Lista de Incidentes](api-list-incidents.md) | Lista de [incidentes](api-incident.md) | Obtener una lista de incidentes.
[Incidente de actualización](api-update-incidents.md) | [Incidentes](api-incident.md) | Actualizar un incidente específico.

## <a name="request-body-response-and-examples"></a>Cuerpo de la solicitud, respuesta y ejemplos

Consulte los respectivos artículos del método para obtener más información sobre cómo construir una solicitud o analizar una respuesta, y para ver ejemplos prácticos.

## <a name="common-properties"></a>Propiedades comunes

Propiedad | Tipo | Descripción
-|-|-
incidentId | largo | IDENTIFICADOR único de incidente.
redirectIncidentId | Nullable Long | IDENTIFICADOR del incidente al que se combinó el incidente actual.
incidentName | cadena | Nombre del incidente.
createdTime | DateTimeOffset | La fecha y hora (en UTC) en que se creó el incidente.
lastUpdateTime | DateTimeOffset | La fecha y hora (en UTC) en que se actualizó por última vez el incidente.
assignedTo | cadena | Propietario del incidente.
severity | Enum | Gravedad del incidente. Los valores posibles son: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` y ```High``` .
status | Enum | Especifica el estado actual del incidente. Los valores posibles son: ```Active``` , ```Resolved``` y ```Redirected``` .
classification | Enum | Especificación del incidente. Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.
cálculo | Enum | Especifica la determinación del incidente. Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Lista de cadenas | Lista de etiquetas de incidente.
alerts | Lista de alertas | Lista de alertas relacionadas. Consulte los ejemplos en la documentación de la API de [incidentes de lista](api-list-incidents.md) .

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre las API de Microsoft 365 defender](api-overview.md)
- [Información general sobre incidentes](incidents-overview.md)
- [API de lista de incidentes](api-list-incidents.md)
- [Actualizar la API de incidentes](api-update-incidents.md)
