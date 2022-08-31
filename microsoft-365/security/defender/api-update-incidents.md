---
title: Actualización de la API de incidentes
description: Obtenga información sobre cómo actualizar incidentes mediante Microsoft 365 Defender API
keywords: update, api, incident
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: d15f7a580964736ebc81bd0dbeed534c4965426b
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480984"
---
# <a name="update-incidents-api"></a>Actualización de la API de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="api-description"></a>Descripción de la API

Novedades propiedades del incidente existente. Las propiedades actualizables son: `status`, `determination`, `classification`, `assignedTo`, `tags`y `comments`.

### <a name="quotas-resource-allocation-and-other-constraints"></a>Cuotas, asignación de recursos y otras restricciones

1. Puede realizar hasta 50 llamadas por minuto o 1500 llamadas por hora antes de alcanzar el umbral de limitación.
2. Solo puede establecer la `determination` propiedad si `classification` está establecida en TruePositive.

Si la solicitud está limitada, devolverá un código de `429` respuesta. El cuerpo de la respuesta indicará el momento en que puede empezar a realizar nuevas llamadas.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Acceso a las API de Microsoft 365 Defender](api-access.md).

Tipo de permiso|Permiso|Nombre para mostrar del permiso
---|---|---
Application|Incident.ReadWrite.All|Leer y escribir todos los incidentes
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

En el cuerpo de la solicitud, proporcione los valores de los campos que se deben actualizar. Las propiedades existentes que no se incluyen en el cuerpo de la solicitud mantendrán sus valores, a menos que tengan que volver a calcularse debido a cambios en los valores relacionados. Para obtener el mejor rendimiento, debe omitir los valores existentes que no han cambiado.

Propiedad|Tipo|Descripción
---|---|---
status|Enum|Especifica el estado actual del incidente. Los valores posibles son: `Active`, `Resolved`y `Redirected`.
assignedTo|string|Propietario del incidente.
classification|Enum|Especificación del incidente. Los valores posibles son: `Unknown`, `FalsePositive` y `TruePositive`.
Determinación|Enum|Especifica la determinación del incidente. Valores posibles: `NotAvailable`, `Apt`, `Malware`, `SecurityPersonnel`, `SecurityTesting`, `UnwantedSoftware`, `Other`.
tags|string List|Lista de etiquetas de incidentes.
comment|string|Comentario que se va a agregar al incidente.

>[!NOTE]
>Alrededor del 29 de agosto de 2022, los valores de determinación de alertas admitidos anteriormente ("Apt" y "SecurityPersonnel") quedarán en desuso y ya no estarán disponibles a través de la API.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve `200 OK`. El cuerpo de la respuesta contendrá la entidad de incidente con las propiedades actualizadas. Si no se encontró un incidente con el identificador especificado, el método devuelve `404 Not Found`.

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

- [Acceso a las API de Microsoft 365 Defender](api-access.md)
- [Más información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
- [API de incidentes](api-incident.md)
- [Lista de Incidentes](api-list-incidents.md)
- [Información general sobre incidentes](incidents-overview.md)
