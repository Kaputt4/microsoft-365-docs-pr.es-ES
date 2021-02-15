---
title: ACTUALIZAR LA API de incidentes
description: Obtenga información sobre cómo actualizar incidentes con la API de Microsoft 365 Defender
keywords: update, api, incident
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
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929075"
---
# <a name="update-incidents-api"></a>ACTUALIZAR LA API de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>Descripción de la API

Actualiza las propiedades del incidente existente. Las propiedades actualizables son: ```status``` ```determination``` , , y ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Cuotas, asignación de recursos y otras restricciones

1. Puede realizar hasta 50 llamadas por minuto o 1500 llamadas por hora antes de alcanzar el umbral de limitación.
2. La propiedad sólo `determination` se puede establecer si se establece en `classification` TruePositive.

Si la solicitud está limitada, devolverá un código `429` de respuesta. El cuerpo de la respuesta indicará la hora en que puede empezar a realizar nuevas llamadas.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, vea Obtener acceso a las [API de Microsoft 365 Defender.](api-access.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
-|-|-
Aplicación | Incident.ReadWrite.All | Leer y escribir todos los incidentes
Delegado (cuenta profesional o educativa) | Incident.ReadWrite | Leer y escribir incidentes

> [!NOTE]
> Al obtener un token con credenciales de usuario, el usuario debe tener permiso para actualizar el incidente en el portal.

## <a name="http-request"></a>Solicitud HTTP

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
-|-|-
Authorization | Cadena | Portador {token}. **Necesario**.
Content-Type | Cadena | application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione los valores de los campos que se deben actualizar. Las propiedades existentes que no se incluyen en el cuerpo de la solicitud mantendrán sus valores, a menos que tengan que volver a calcularse debido a cambios en los valores relacionados. Para obtener el mejor rendimiento, debe omitir los valores existentes que no han cambiado.

Propiedad | Tipo | Description
-|-|-
status | Enum | Especifica el estado actual de la alerta. Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .
assignedTo | string | Propietario del incidente.
classification | Enum | Especificación de la alerta. Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.
determinación | Enum | Especifica la determinación de la alerta. Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | lista de cadenas | Lista de etiquetas de incidentes.

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve `200 OK` . El cuerpo de la respuesta contendrá la entidad del incidente con propiedades actualizadas. Si no se encontró un incidente con el identificador especificado, el método devuelve `404 Not Found` .

## <a name="example"></a>Ejemplo

**Solicitud**

Este es un ejemplo de la solicitud.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Respuesta**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a>Artículos relacionados

- [Obtener acceso a las API de Microsoft 365 Defender](api-access.md)
- [Más información sobre los límites de la API y las licencias](api-terms.md)
- [Comprender los códigos de error](api-error-codes.md)
- [API de incidentes](api-incident.md)
- [Lista de Incidentes](api-list-incidents.md)
- [Información general sobre incidentes](incidents-overview.md)
