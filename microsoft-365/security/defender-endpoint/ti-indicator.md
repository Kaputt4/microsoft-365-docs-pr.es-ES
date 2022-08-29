---
title: Tipo de recurso indicador
description: Especifique los detalles de la entidad y defina la expiración del indicador mediante Microsoft Defender para punto de conexión.
keywords: apis, api admitidas, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: dcdba63fe99d092f2ce6a9839a94f5e4c297ee66
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67330771"
---
# <a name="indicator-resource-type"></a>Tipo de recurso indicador

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

- Consulte la [página Indicadores](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) correspondiente en el portal.

Método|Tipo de valor devuelto|Descripción
:---|:---|:---
[Mostrar indicadores](get-ti-indicators-collection.md)|[Indicador](ti-indicator.md) Colección|[Entidades de indicador](ti-indicator.md) de lista.
[Enviar indicador](post-ti-indicator.md)|[Indicador](ti-indicator.md)|Enviar o actualizar la entidad [Indicator](ti-indicator.md) .
[Indicadores de importación](import-ti-indicators.md)|[Indicador](ti-indicator.md) Colección|Enviar o actualizar entidades [de indicadores](ti-indicator.md) .
[Eliminar indicador](delete-ti-indicator-by-id.md)|Sin contenido|Elimina la entidad [Indicator](ti-indicator.md) .

## <a name="properties"></a>Propiedades

Propiedad|Tipo|Descripción
:---|:---|:---
id|Cadena|Identidad de la entidad [Indicator](ti-indicator.md) .
indicatorValue|Cadena|Valor del [indicador](ti-indicator.md).
indicatorType|Enum|Tipo del indicador. Los valores posibles son: "FileSha1", "FileSha256", "FileMd5", "CertificateThumbprint", "IpAddress", "DomainName" y "Url".
aplicación|Cadena|Aplicación asociada al indicador.
acción|Enum|Acción que se realizará si el indicador se detectará en la organización. Los valores posibles son: "Warn", "Block", "Audit", "Alert", "AlertAndBlock", "BlockAndRemediate" y "Allowed".
|externalID|Cadena|Identificador que el cliente puede enviar en la solicitud de correlación personalizada.|
Sourcetype|Enum|"Usuario" en caso de que el indicador creado por un usuario (por ejemplo, desde el portal), "AadApp" en caso de que se envíe mediante una aplicación automatizada a través de la API.
createdBySource|string|Nombre del usuario o aplicación que envió el indicador.
createdBy|String|Identidad única del usuario o aplicación que envió el indicador.
lastUpdatedBy|Cadena|Identidad del usuario o aplicación que actualizó por última vez el indicador.
creationTimeDateTimeUtc|DateTimeOffset|Fecha y hora en que se creó el indicador.
expirationTime|DateTimeOffset|Tiempo de expiración del indicador.
lastUpdateTime|DateTimeOffset|La última vez que se actualizó el indicador.
severity|Enum|Gravedad del indicador. Los valores posibles son: "Informativo", "Bajo", "Medio" y "Alto".
title|Cadena|Título del indicador.
description|Cadena|Descripción del indicador.
recommendedActions|Cadena|Acciones recomendadas para el indicador.
rbacGroupNames|Lista de cadenas|Nombres de grupos de dispositivos RBAC donde el indicador está expuesto y activo. Lista vacía en caso de que se exponga a todos los dispositivos.
rbacGroupIds|Lista de cadenas|El identificador del grupo de dispositivos RBAC es donde se expone y activa el indicador. Lista vacía en caso de que se exponga a todos los dispositivos.
generateAlert|Enum|**True** si se requiere la generación de alertas, **False** si este indicador no debe generar una alerta.

## <a name="indicator-types"></a>Tipos de indicador

Los tipos de acción de indicador admitidos por la API son:

- Permitido
- Auditoría
- Bloquear
- BlockAndRemediate
- Advertir (solo Defender for Cloud Apps)

Para obtener más información sobre la descripción de los tipos de acción de respuesta, vea [Crear indicadores](manage-indicators.md).

> [!Note]
>
> Las acciones de respuesta anteriores (AlertAndBlock y Alert) se admitirán hasta enero de 2022. Después de esta fecha, todos los clientes deben usar uno de los tipos de acción enumerados anteriormente.

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
