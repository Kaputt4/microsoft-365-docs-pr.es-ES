---
title: Actualizar la API de incidentes
description: Obtenga información sobre cómo actualizar incidentes con la API de Microsoft 365 defender
keywords: actualización, API, incidente
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719409"
---
# <a name="update-incidents-api"></a>Actualizar la API de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>Descripción de la API

Actualiza las propiedades de un incidente existente. Las propiedades actualizables son: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` y ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Cuotas, asignación de recursos y otras restricciones

1. Puede realizar hasta 50 llamadas por minuto o 1500 llamadas por hora antes de alcanzar el umbral de limitación.
2. Puede establecer la `determination` propiedad solo si `classification` está establecida en TruePositive.

Si se limita la solicitud, se devolverá un `429` código de respuesta. El cuerpo de la respuesta indicará la hora en la que puede empezar a realizar nuevas llamadas.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de Microsoft 365 defender](api-access.md).

Tipo de permiso | Permiso | Nombre para mostrar del permiso
-|-|-
Aplicación | Incident. ReadWrite. All | Leer y escribir todos los incidentes
Delegado (cuenta profesional o educativa) | Incident. ReadWrite | Leer y escribir incidentes

> [!NOTE]
> Al obtener un token con credenciales de usuario, el usuario debe tener permiso para actualizar el incidente en el portal.

## <a name="http-request"></a>Solicitud HTTP

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
-|-|-
Authorization | Cadena | {Token} de portador. **Necesario**.
Content-Type | Cadena | application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione los valores de los campos que se deben actualizar. Las propiedades existentes que no se incluyen en el cuerpo de la solicitud conservarán sus valores, a menos que se deban volver a calcular debido a cambios en los valores relacionados. Para obtener el mejor rendimiento, debe omitir los valores existentes que no han cambiado.

Propiedad | Tipo | Descripción
-|-|-
status | Enum | Especifica el estado actual de la alerta. Los valores posibles son: ```Active``` , ```Resolved``` y ```Redirected``` .
assignedTo | cadena | Propietario del incidente.
classification | Enum | Especificación de la alerta. Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.
cálculo | Enum | Especifica la determinación de la alerta. Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Lista de cadenas | Lista de etiquetas de incidente.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve `200 OK` . El cuerpo de la respuesta contendrá la entidad incidente con propiedades actualizadas. Si no se ha encontrado un incidente con el identificador especificado, el método devuelve `404 Not Found` .

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

- [Acceso a las API de Microsoft 365 defender](api-access.md)
- [Obtenga información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
- [API de incidentes](api-incident.md)
- [Lista de Incidentes](api-list-incidents.md)
- [Información general sobre incidentes](incidents-overview.md)
