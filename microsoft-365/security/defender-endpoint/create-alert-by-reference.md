---
title: Creación de una alerta a partir de event API
description: Obtenga información sobre cómo usar la API De creación de alertas para crear una nueva alerta sobre el evento en Microsoft Defender para punto de conexión.
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
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 817bfec55a38cef0404c392bce9765d1aef14686
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623154"
---
# <a name="create-alert-api"></a>Creación de la API de alertas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API

Crea una nueva [alerta](alerts.md) sobre **el evento**.

- **Microsoft Defender para punto de conexión evento** es necesario para la creación de alertas.
- Debe proporcionar tres parámetros del evento en la solicitud: **Hora del evento**, Id. **de máquina** e **Id. de informe**. Vea el ejemplo abajo.
- Puede usar un evento que se encuentra en Advanced Hunting API o Portal.
- Si existe una alerta abierta en el mismo dispositivo con el mismo título, la nueva alerta creada se combinará con ella.
- Una investigación automática se inicia automáticamente en las alertas creadas a través de la API.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 15 llamadas por minuto.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar del permiso
:---|:---|:---
Application | Alert.ReadWrite.All | "Leer y escribir todas las alertas"
Delegado (cuenta profesional o educativa) | Alert.ReadWrite | "Alertas de lectura y escritura"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Investigación de alertas" (para obtener más información, vea [Crear y administrar roles](user-roles.md) )
> - El usuario debe tener acceso al dispositivo asociado a la alerta, en función de la configuración del grupo de dispositivos (para obtener más información, consulte [Creación y administración de grupos de dispositivos](machine-groups.md)).
>
> La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.
Content-Type | Cadena | application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En el cuerpo de la solicitud, proporcione los siguientes valores (todos son necesarios):

Propiedad | Tipo | Descripción
:---|:---|:---
eventTime | DateTime(UTC) | Hora exacta del evento como cadena, obtenida de la búsqueda avanzada. Por ejemplo,  ```2018-08-03T16:45:21.7115183Z``` **Obligatorio**.
reportId | Cadena | El reportId del evento, tal como se obtiene de la búsqueda avanzada. **Necesario**.
machineId | Cadena | Identificador del dispositivo en el que se identificó el evento. **Necesario**.
severity | Cadena | Gravedad de la alerta. Los valores de propiedad son: "Low", "Medium" y "High". **Necesario**.
title | Cadena | Título de la alerta. **Necesario**.
description | Cadena | Descripción de la alerta. **Necesario**.
recommendedAction| Cadena | El responsable de seguridad debe realizar esta acción al analizar la alerta. **Necesario**.
categoría| Cadena | Categoría de la alerta. Los valores de propiedad son: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK y un nuevo objeto [de alerta](alerts.md) en el cuerpo de la respuesta. Si no se encontró el evento con las propiedades especificadas (_reportId_, _eventTime_ y _machineId_): 404 No encontrado.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Este es un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
