---
title: Actualización de la API de entidad de alerta
description: Obtenga información sobre cómo actualizar una alerta de Microsoft Defender para punto de conexión mediante esta API. Puede actualizar las propiedades status, determination, classification y assignedTo.
keywords: apis, graph api, api admitidas, get, alert, information, id
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 99f17d9aacb67214703a4af2647385fa1778e88a
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68221772"
---
# <a name="update-alert"></a>Actualizar alerta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API
Novedades propiedades de [la alerta](alerts.md) existente.

El envío de **comentario** está disponible con o sin actualizar las propiedades.

Las propiedades actualizables son: `status`, `determination`, `classification`y `assignedTo`.

## <a name="limitations"></a>Limitaciones

1. Puede actualizar las alertas que están disponibles en la API. Para obtener más información, consulte [Lista de alertas](get-alerts.md).
2. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Alerts.ReadWrite.All|"Leer y escribir todas las alertas"
Delegado (cuenta profesional o educativa)|Alert.ReadWrite|"Alertas de lectura y escritura"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Investigación de alertas" (para obtener más información, vea [Crear y administrar roles](user-roles.md) )
> - El usuario debe tener acceso al dispositivo asociado a la alerta, en función de la configuración del grupo de dispositivos (para obtener más información, consulte [Creación y administración de grupos de dispositivos](machine-groups.md)).
>
> La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión.

## <a name="http-request"></a>Solicitud HTTP

```http
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|Cadena|application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En el cuerpo de la solicitud, proporcione los valores de los campos pertinentes que se deben actualizar.

Las propiedades existentes que no se incluyen en el cuerpo de la solicitud mantendrán sus valores anteriores o se recalcularán en función de los cambios realizados en otros valores de propiedad.

Para obtener el mejor rendimiento, no debe incluir valores existentes que no hayan cambiado.

Propiedad|Tipo|Descripción|
:---|:---|:---
Estado|Cadena|Especifica el estado actual de la alerta. Los valores de propiedad son: "New", "InProgress" y "Resolved".|
assignedTo|Cadena|Propietario de la alerta|
Clasificación|Cadena|Especifica la especificación de la alerta. Los valores de propiedad son: `TruePositive`, `Informational, expected activity`y `FalsePositive`.|
Determinación|Cadena|Especifica la determinación de la alerta. <p>Los valores de determinación posibles para cada clasificación son: <br><li> <b>Verdadero positivo</b>: `Multistage attack` (MultiStagedAttack), `Malicious user activity` (MaliciousUserActivity), `Compromised account` (CompromisedUser): considere la posibilidad de cambiar el nombre de la enumeración en la API pública en consecuencia, `Malware` (Malware), `Phishing` (Phishing), `Unwanted software` (UnwantedSoftware) y `Other` (Other). <li> <b>Actividad informativa y esperada:</b> `Security test` (SecurityTesting), `Line-of-business application` (LineOfBusinessApplication), `Confirmed activity` (ConfirmedUserActivity): considere la posibilidad de cambiar el nombre de la enumeración en la API pública en consecuencia y `Other` (Otros). <li>  <b>Falso positivo:</b> `Not malicious` (Limpiar): considere la posibilidad de cambiar el nombre de la enumeración en la API pública en consecuencia, `Not enough data to validate` (InsufficientData) y `Other` (Other).|
Comentario|Cadena|Comentario que se va a agregar a la alerta.|

>[!NOTE]
>Alrededor del 29 de agosto de 2022, los valores de determinación de alertas admitidos anteriormente ("Apt" y "SecurityPersonnel") estarán en desuso y ya no estarán disponibles a través de la API.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK y la entidad [de alerta](alerts.md) en el cuerpo de la respuesta con las propiedades actualizadas. Si no se encontró la alerta con el identificador especificado: 404 No encontrado.

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
