---
title: API de entidades de alertas de actualización por lotes
description: Obtenga información sobre cómo actualizar Microsoft Defender para punto de conexión alertas en un lote mediante esta API. Puede actualizar las propiedades status, determination, classification y assignedTo.
keywords: apis, graph api, api admitidas, get, alert, information, id
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
ms.technology: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 8c7579eef9c3e688e16c66bcb1a6031715b6a6a9
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698295"
---
# <a name="batch-update-alerts"></a>Alertas de actualización por lotes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API

Novedades propiedades de un lote de [alertas](alerts.md) existentes.

El envío de **comentario** está disponible con o sin actualizar las propiedades.

Las propiedades actualizables son: `status`, `determination``classification` y `assignedTo`.

## <a name="limitations"></a>Limitaciones

1. Puede actualizar las alertas que están disponibles en la API. Consulte [Lista de alertas](get-alerts.md) para obtener más información.
2. Las limitaciones de velocidad de esta API son 10 llamadas por minuto y 500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar del permiso
:---|:---|:---
Application | Alert.ReadWrite.All | "Leer y escribir todas las alertas"
Delegado (cuenta profesional o educativa) | Alert.ReadWrite | "Alertas de lectura y escritura"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Investigación de alertas" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).
> - El usuario debe tener acceso al dispositivo asociado a la alerta, en función de la configuración del grupo de dispositivos (consulte [Creación y administración de grupos de dispositivos](machine-groups.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.
Content-Type | Cadena | application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En el cuerpo de la solicitud, proporcione los identificadores de las alertas que se van a actualizar y los valores de los campos pertinentes que desea actualizar para estas alertas.

Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad.

Para obtener el mejor rendimiento no debe incluir valores existentes que no hayan cambiado.

Propiedad | Tipo | Descripción
:---|:---|:---
alertIds | Cadena de lista&lt;&gt;| Una lista de los identificadores de las alertas que se van a actualizar. **Required**
status | Cadena | Especifica el estado actualizado de las alertas especificadas. Los valores de propiedad son: "New", "InProgress" y "Resolved".
assignedTo | Cadena | Propietario de las alertas especificadas
classification | String | Especifica la especificación de las alertas especificadas. Los valores de propiedad son: "True positive", "Informational, expected activity" y "False positive".
Determinación | Cadena | Especifica la determinación de las alertas especificadas. Los valores de propiedad son: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
comment | String | Comentario que se va a agregar a las alertas especificadas.

>[!NOTE]
>Alrededor del 29 de agosto de 2022, los valores de determinación de alertas admitidos anteriormente ("Apt" y "SecurityPersonnel") quedarán en desuso y ya no estarán disponibles a través de la API.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK, con un cuerpo de respuesta vacío.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
