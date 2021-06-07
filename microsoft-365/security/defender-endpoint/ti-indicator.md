---
title: Tipo de recurso Indicator
description: Especifique los detalles de la entidad y defina la expiración del indicador mediante Microsoft Defender para endpoint.
keywords: apis, api admitidas, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771386"
---
# <a name="indicator-resource-type"></a>Tipo de recurso Indicator

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Vea la página [Indicadores correspondiente](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) en el portal. 

Método|Tipo de valor devuelto |Descripción
:---|:---|:---
[Mostrar indicadores](get-ti-indicators-collection.md) | [Indicador](ti-indicator.md) Colección | Enumerar [entidades de](ti-indicator.md) indicador.
[Enviar indicador](post-ti-indicator.md) | [Indicador](ti-indicator.md) | Enviar o actualizar entidad [Indicator.](ti-indicator.md)
[Indicadores de importación](import-ti-indicators.md) | [Indicador](ti-indicator.md) Colección | Enviar o actualizar [entidades de](ti-indicator.md) indicadores.
[Eliminar indicador](delete-ti-indicator-by-id.md) | Sin contenido | Elimina la [entidad Indicator.](ti-indicator.md)


## <a name="properties"></a>Propiedades
Propiedad |  Tipo    |   Descripción
:---|:---|:---
id | Cadena | Identidad de la [entidad Indicator.](ti-indicator.md)
indicatorValue | Cadena | El valor del [indicador](ti-indicator.md).
indicatorType | Enum | Tipo del indicador. Los valores posibles son: "FileSha1", "FileSha256", "IpAddress", "DomainName" y "Url".
aplicación | Cadena | La aplicación asociada al indicador. 
acción | Enum | La acción que se realizará si el indicador se detectará en la organización. Los valores posibles son: "Alert", "AlertAndBlock" y "Allowed".
sourceType | Enum | "Usuario" en caso de que el indicador creado por un usuario (por ejemplo, desde el portal), "AadApp" en caso de que se haya enviado mediante una aplicación automatizada a través de la API.
source | cadena | Nombre del usuario o aplicación que envió el indicador.
createdBy | String | Identidad única del usuario/aplicación que envió el indicador.
lastUpdatedBy | Cadena | Identidad del usuario/aplicación que actualizó por última vez el indicador.
creationTimeDateTimeUtc | DateTimeOffset | La fecha y hora en que se creó el indicador.
expirationTime | DateTimeOffset | La hora de expiración del indicador.
lastUpdateTime | DateTimeOffset | La última vez que se actualizó el indicador.
severity | Enum | Gravedad del indicador. los valores posibles son: "Informational", "Low", "Medium" y "High".
title | Cadena | Título del indicador.
description | Cadena | Descripción del indicador.
recommendedActions | Cadena | Acciones recomendadas para el indicador.
rbacGroupNames | Lista de cadenas | Nombres de grupo de dispositivo RBAC donde se expone y activa el indicador. Lista vacía en caso de que se exponga a todos los dispositivos.


## <a name="json-representation"></a>Representación json

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
