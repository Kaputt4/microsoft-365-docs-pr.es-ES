---
title: Microsoft 365 Defender incidentes API y el tipo de recurso incidente
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Incidente en Microsoft 365 Defender
keywords: incidentes, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572590"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender incidentes API y el tipo de recurso incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Un [incidente](incidents-overview.md) es una colección de alertas relacionadas que ayudan a describir un ataque. Los eventos de diferentes entidades de la organización se agregan automáticamente por Microsoft 365 Defender. Puede usar la API de incidentes para tener acceso mediante programación a los incidentes de su organización y a las alertas relacionadas.

## <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora. Cada método también tiene sus propias cuotas. Para obtener más información sobre las cuotas específicas del método, consulte el artículo correspondiente para el método que desea usar.

Un `429` código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por el tiempo de ejecución asignado. El cuerpo de respuesta incluirá el tiempo hasta que se restablezca la cuota a la que llegó.

## <a name="permissions"></a>Permisos

La API de incidentes requiere diferentes tipos de permisos para cada uno de sus métodos. Para obtener más información acerca de los permisos necesarios, consulte el artículo del método respectivo.

## <a name="methods"></a>Métodos

Método | Tipo de valor devuelto | Descripción
-|-|-
[Lista de Incidentes](api-list-incidents.md) | [Lista de incidentes](api-incident.md) | Obtenga una lista de incidentes.
[Incidente de actualización](api-update-incidents.md) | [Incidente](api-incident.md) | Actualice un incidente específico.

## <a name="request-body-response-and-examples"></a>Solicitar cuerpo, respuesta y ejemplos

Consulte los artículos de método respectivos para obtener más detalles sobre cómo construir una solicitud o analizar una respuesta y ejemplos prácticos.

## <a name="common-properties"></a>Propiedades comunes

Propiedad | Tipo | Descripción
-|-|-
incidenteId | largo | Id. único del incidente.
redirectIncidentId | nullable largo | El id. de incidente al que se fusionó el incidente actual.
incidentName | cadena | El nombre del incidente.
creóTime | DateTimeOffset | La fecha y hora (en UTC) se creó el incidente.
lastUpdateTime | DateTimeOffset | La fecha y hora (en UTC) el incidente se actualizó por última vez.
assignedTo | cadena | Propietario del incidente.
severity | Enum | Gravedad del incidente. Los valores posibles son: ```UnSpecified``` , , , y ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Especifica el estado actual del incidente. Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .
classification | Enum | Especificación del incidente. Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.
determinación | Enum | Especifica la determinación del incidente. Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Lista de cuerdas | Lista de etiquetas incidente.
comments | Lista de comentarios de incidentes | El objeto Comment de incidente contiene: cadena de comentario, cadena createdBy y hora de fecha createTime.
alerts | Lista de alertas | Lista de alertas relacionadas. Consulte ejemplos en La documentación de la API [De incidentes](api-list-incidents.md) de lista.

## <a name="related-articles"></a>Artículos relacionados

- [Microsoft 365 Descripción general de las API de Defender](api-overview.md)
- [Información general sobre incidentes](incidents-overview.md)
- [Enumerar incidentes API](api-list-incidents.md)
- [Actualizar api incidentes](api-update-incidents.md)
