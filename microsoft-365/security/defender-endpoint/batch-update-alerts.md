---
title: API de entidades de alerta de actualización por lotes
description: Obtenga información sobre cómo actualizar alertas de Microsoft Defender para endpoints en un lote mediante esta API. Puede actualizar las propiedades status, determination, classification y assignedTo.
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
ms.technology: mde
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167087"
---
# <a name="batch-update-alerts"></a>Alertas de actualización por lotes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Actualiza las propiedades de un lote de alertas [existentes](alerts.md).
<br>El envío **de comentarios** está disponible con o sin actualizar propiedades.
<br>Las propiedades actualizables son: `status` `determination` , y `classification` `assignedTo` .


## <a name="limitations"></a>Limitaciones
1. Puede actualizar las alertas que están disponibles en la API. Vea [Enumerar alertas](get-alerts.md) para obtener más información.
2. Las limitaciones de velocidad para esta API son 10 llamadas por minuto y 500 llamadas por hora.


## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   Alerts.ReadWrite.All |  'Leer y escribir todas las alertas'
Delegado (cuenta profesional o educativa) | Alert.ReadWrite | 'Leer y escribir alertas'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
>- El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)

## <a name="http-request"></a>Solicitud HTTP
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.
Content-Type | Cadena | application/json. **Necesario**.


## <a name="request-body"></a>Cuerpo de la solicitud
En el cuerpo de la solicitud, proporcione los IDs de las alertas que se actualizarán y los valores de los campos relevantes que desea actualizar para estas alertas.
<br>Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad. 
<br>Para obtener el mejor rendimiento no debe incluir valores existentes que no hayan cambiado.

Propiedad | Tipo | Descripción
:---|:---|:---
alertIds | Cadena de &lt; lista&gt;| Una lista de los IDs de las alertas que se actualizarán. **Required**
status | Cadena | Especifica el estado actualizado de las alertas especificadas. Los valores de propiedad son: 'New', 'InProgress' y 'Resolved'.
assignedTo | Cadena | Propietario de las alertas especificadas
classification | String | Especifica la especificación de las alertas especificadas. Los valores de propiedad son: 'Unknown', 'FalsePositive', 'TruePositive'. 
determinación | Cadena | Especifica la determinación de las alertas especificadas. Los valores de propiedad son: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
comment | String | Comentario que se agregará a las alertas especificadas.

## <a name="response"></a>Respuesta
Si se realiza correctamente, este método devuelve 200 Ok, con un cuerpo de respuesta vacío.


## <a name="example"></a>Ejemplo:

**Solicitud**

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
