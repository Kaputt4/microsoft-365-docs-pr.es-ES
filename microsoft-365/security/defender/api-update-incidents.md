---
title: ACTUALIZAR API de incidentes
description: Obtenga información sobre cómo actualizar incidentes con Microsoft 365 Defender API
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
ms.custom: api
ms.openlocfilehash: 447a4b5eb3f4eb521e7cc3bd2df23a42f16d2ef1
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2022
ms.locfileid: "62171855"
---
# <a name="update-incidents-api"></a>ACTUALIZAR LA API de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="api-description"></a>Descripción de la API

Actualiza las propiedades del incidente existente. Las propiedades actualizables son: `status` , , , , y `determination` `classification` `assignedTo` `tags` `comments` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Cuotas, asignación de recursos y otras restricciones

1. Puede hacer hasta 50 llamadas por minuto o 1500 llamadas por hora antes de alcanzar el umbral de limitación.
2. Solo puede establecer la `determination` propiedad si está establecida en `classification` TruePositive.

Si la solicitud está limitada, devolverá un `429` código de respuesta. El cuerpo de la respuesta indicará la hora en que puede empezar a realizar llamadas nuevas.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, vea [Access the Microsoft 365 Defender API](api-access.md).

Tipo de permiso|Permiso|Nombre para mostrar de permisos
---|---|---
Aplicación|Incident.ReadWrite.All|Leer y escribir todos los incidentes
Delegado (cuenta profesional o educativa)|Incident.ReadWrite|Incidentes de lectura y escritura

> [!NOTE]
> Al obtener un token con credenciales de usuario, el usuario debe tener permiso para actualizar el incidente en el portal.

## <a name="http-request"></a>Solicitud HTTP

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
---|---|---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|Cadena|application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En el cuerpo de la solicitud, proporcione los valores de los campos que deben actualizarse. Las propiedades existentes que no se incluyen en el cuerpo de la solicitud mantendrán sus valores, a menos que tengan que volver a calcularse debido a los cambios en los valores relacionados. Para obtener el mejor rendimiento, debe omitir los valores existentes que no han cambiado.

Propiedad|Tipo|Descripción
---|---|---
status|Enum|Especifica el estado actual del incidente. Los valores posibles son: `Active` `Resolved` , y `Redirected` .
assignedTo|string|Propietario del incidente.
classification|Enum|Especificación del incidente. Los valores posibles son: `Unknown`, `FalsePositive` y `TruePositive`.
determinación|Enum|Especifica la determinación del incidente. Valores posibles: `NotAvailable`, `Apt`, `Malware`, `SecurityPersonnel`, `SecurityTesting`, `UnwantedSoftware`, `Other`.
tags|lista de cadenas|Lista de etiquetas de incidentes.
comment|string|Comentario que se agregará al incidente.

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve `200 OK` . El cuerpo de la respuesta contendrá la entidad incident con propiedades actualizadas. Si no se encontró un incidente con el identificador especificado, el método devuelve `404 Not Found` .

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Este es un ejemplo de la solicitud.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

### <a name="response-example"></a>Ejemplo de respuesta

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>Artículos relacionados

- [Obtener acceso a Microsoft 365 Defender API de acceso](api-access.md)
- [Más información sobre los límites de api y las licencias](api-terms.md)
- [Comprender códigos de error](api-error-codes.md)
- [API de incidentes](api-incident.md)
- [Lista de Incidentes](api-list-incidents.md)
- [Información general sobre incidentes](incidents-overview.md)
