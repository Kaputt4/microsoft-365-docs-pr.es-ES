---
title: Crear alerta desde la API de eventos
description: Obtén información sobre cómo usar la API crear alertas para crear una nueva alerta encima del evento en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, alert, information, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7f8d3b10cee0b3c4a561dfd1f7567fa9818e7686
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289468"
---
# <a name="create-alert-api"></a>Crear API de alertas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API

Crea una [nueva alerta](alerts.md) en la parte superior del **evento**.

- **Se requiere Microsoft Defender para el evento endpoint** para la creación de alertas.
- Deberá proporcionar 3 parámetros del evento en la solicitud: **Hora del** evento , **Id. de** máquina e **Id. de informe.** Vea el ejemplo abajo.
- Puedes usar un evento que se encuentra en la API de búsqueda avanzada o portal.
- Si existe una alerta abierta en el mismo dispositivo con el mismo título, la nueva alerta creada se combinará con ella.
- Una investigación automática se inicia automáticamente en alertas creadas a través de la API.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad para esta API son 15 llamadas por minuto.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
:---|:---|:---
Aplicación | Alerts.ReadWrite.All | 'Leer y escribir todas las alertas'
Delegado (cuenta profesional o educativa) | Alert.ReadWrite | 'Leer y escribir alertas'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
> - El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.
Content-Type | Cadena | application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione los siguientes valores (todos son necesarios):

Propiedad | Tipo | Descripción
:---|:---|:---
eventTime | DateTime(UTC) | La hora precisa del evento como cadena, como se obtiene de la búsqueda avanzada. Por ejemplo, Obligatorio ```2018-08-03T16:45:21.7115183Z``` .
reportId | Cadena | El reportId del evento, como se obtiene de la búsqueda avanzada. **Necesario**.
machineId | Cadena | Id. del dispositivo en el que se identificó el evento. **Necesario**.
severity | Cadena | Gravedad de la alerta. Los valores de propiedad son: 'Low', 'Medium' y 'High'. **Necesario**.
title | Cadena | Título de la alerta. **Necesario**.
description | Cadena | Descripción de la alerta. **Necesario**.
recommendedAction| Cadena | Acción recomendada por el responsable de seguridad al analizar la alerta. **Necesario**.
categoría| Cadena | Categoría de la alerta. Los valores de propiedad son: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200 Ok y un nuevo [objeto alert](alerts.md) en el cuerpo de la respuesta. If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

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
