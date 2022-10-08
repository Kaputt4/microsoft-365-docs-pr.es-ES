---
title: Microsoft 365 Defender API de incidentes y el tipo de recurso incidents
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Incidents en Microsoft 365 Defender
keywords: incidente, incidentes, API
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: 749d4a5c5884275a664a032b1f423e7e0fbdfafc
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68062152"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a>Microsoft 365 Defender API de incidentes y el tipo de recurso incidents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Un [incidente](incidents-overview.md) es una colección de alertas relacionadas que ayudan a describir un ataque. Los eventos de diferentes entidades de la organización se agregan automáticamente mediante Microsoft 365 Defender. Puede usar la API de incidentes para acceder de forma programática a los incidentes de su organización y a las alertas relacionadas.

## <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora. Cada método también tiene sus propias cuotas. Para obtener más información sobre las cuotas específicas del método, consulte el artículo correspondiente para el método que desea usar.

Un `429` código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo de ejecución asignado. El cuerpo de la respuesta incluirá el tiempo hasta que se restablezca la cuota que alcanzó.

## <a name="permissions"></a>Permisos

La API de incidentes requiere diferentes tipos de permisos para cada uno de sus métodos. Para obtener más información sobre los permisos necesarios, consulte el artículo del método correspondiente.

## <a name="methods"></a>Métodos

Método | Tipo de valor devuelto | Descripción
-|-|-
[Lista de Incidentes](api-list-incidents.md) | [Lista de incidentes](api-incident.md) | Obtenga una lista de incidentes.
[Incidente de actualización](api-update-incidents.md) | [Incidente](api-incident.md) | Actualice un incidente específico.
[Obtener incidente](api-get-incident.md) | [Incidente](api-incident.md) | Obtenga un único incidente.

## <a name="request-body-response-and-examples"></a>Cuerpo de la solicitud, respuesta y ejemplos

Consulte los artículos del método correspondiente para obtener más detalles sobre cómo construir una solicitud o analizar una respuesta, y para obtener ejemplos prácticos.

## <a name="common-properties"></a>Propiedades comunes

Propiedad | Tipo | Descripción
-|-|-
incidentId | largo | Identificador único del incidente.
redirectIncidentId | long que admite valores NULL | Identificador de incidente al que se combinó el incidente actual.
incidentName | string | Nombre del incidente.
createdTime | DateTimeOffset | Fecha y hora (en UTC) en la que se creó el incidente.
lastUpdateTime | DateTimeOffset | Fecha y hora (en UTC) que el incidente se actualizó por última vez.
assignedTo | string | Propietario del incidente.
severity | Enum | Gravedad del incidente. Los valores posibles son: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```y ```High```.
status | Enum | Especifica el estado actual del incidente. Los valores posibles son ```Active```, ```InProgress```, ```Resolved``` y ```Redirected```
classification | Enum | Especificación del incidente. Los valores posibles son: `TruePositive`, `Informational, expected activity`y `FalsePositive`.
Determinación | Enum | Especifica la determinación del incidente. <p>Los valores de determinación posibles para cada clasificación son: <br><li> <b>Verdadero positivo</b>: `Multistage attack` (MultiStagedAttack), `Malicious user activity` (MaliciousUserActivity), `Compromised account` (CompromisedUser): considere la posibilidad de cambiar el nombre de la enumeración en la API pública en consecuencia, `Malware` (Malware), `Phishing` (Phishing), `Unwanted software` (UnwantedSoftware) y `Other` (Other). <li> <b>Actividad informativa y esperada:</b> `Security test` (SecurityTesting), `Line-of-business application` (LineOfBusinessApplication), `Confirmed activity` (ConfirmedUserActivity): considere la posibilidad de cambiar el nombre de la enumeración en la API pública en consecuencia y `Other` (Otros). <li>  <b>Falso positivo:</b> `Not malicious` (Limpiar): considere la posibilidad de cambiar el nombre de la enumeración en la API pública en consecuencia, `Not enough data to validate` (InsufficientData) y `Other` (Other).
tags | lista de cadenas | Lista de etiquetas de incidentes.
comments | Lista de comentarios de incidentes | El objeto Incident Comment contiene: cadena de comentario, cadena createdBy y fecha y hora de createTime.
alertas | lista de alertas | Lista de alertas relacionadas. Consulte ejemplos en [la documentación de la API De lista de incidentes](api-list-incidents.md) .

>[!NOTE]
>Alrededor del 29 de agosto de 2022, los valores de determinación de alertas admitidos anteriormente ("Apt" y "SecurityPersonnel") estarán en desuso y ya no estarán disponibles a través de la API.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Información general sobre incidentes](incidents-overview.md)
- [API de lista de incidentes](api-list-incidents.md)
- [Actualización de la API de incidentes](api-update-incidents.md)
