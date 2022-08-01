---
title: ACTUALIZAR API de entidad de alerta
description: Obtén información sobre cómo actualizar una alerta de Microsoft Defender para endpoint mediante esta API. Puede actualizar las propiedades status, determination, classification y assignedTo.
keywords: apis, api de gráficos, api admitidas, get, alert, information, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b6154c4ed2374fd75416fee1107444ec72c15ddd
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61164195"
---
# <a name="update-alert"></a>Actualizar alerta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API
Actualiza las propiedades [de](alerts.md)alert existente .

El envío **de comentarios** está disponible con o sin actualizar propiedades.

Las propiedades actualizables son: `status` `determination` , , y `classification` `assignedTo` .

## <a name="limitations"></a>Limitaciones

1. Puede actualizar las alertas disponibles en la API. Para obtener más información, vea [Enumerar alertas](get-alerts.md).
2. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Alerts.ReadWrite.All|'Leer y escribir todas las alertas'
Delegado (cuenta profesional o educativa)|Alert.ReadWrite|'Leer y escribir alertas'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas" (Para obtener más información, vea [Crear y administrar roles](user-roles.md) )
> - El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (Para obtener más información, vea [Crear y administrar grupos de dispositivos](machine-groups.md))

## <a name="http-request"></a>Solicitud HTTP

```http
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|Cadena|application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione los valores de los campos relevantes que deben actualizarse.

Las propiedades existentes que no se incluyen en el cuerpo de la solicitud mantendrán sus valores anteriores o se recalcularán en función de los cambios realizados en otros valores de propiedad.

Para obtener el mejor rendimiento, no debe incluir valores existentes que no hayan cambiado.

Propiedad|Tipo|Description
:---|:---|:---
Estado|Cadena|Especifica el estado actual de la alerta. Los valores de propiedad son: 'New', 'InProgress' y 'Resolved'.
assignedTo|Cadena|Propietario de la alerta
Clasificación|Cadena|Especifica la especificación de la alerta. Los valores de propiedad son: 'Unknown', 'FalsePositive', 'TruePositive'.
Determinación|Cadena|Especifica la determinación de la alerta. Los valores de propiedad son: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
Comentario|Cadena|Comentario que se agregará a la alerta.

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200 Ok y la entidad [alert](alerts.md) en el cuerpo de la respuesta con las propiedades actualizadas. Si no se encontró la alerta con el identificador especificado: 404 No se encontró.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Este es un ejemplo de la solicitud.

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
