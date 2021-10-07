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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d7805ad7a2c1aae750b6588a6dd2c4141c9b93c3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191640"
---
# <a name="indicator-resource-type"></a>Tipo de recurso Indicator

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

- Vea la página [Indicadores correspondiente](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) en el portal.

Método|Tipo de valor devuelto|Descripción
:---|:---|:---
[Mostrar indicadores](get-ti-indicators-collection.md)|[Indicador](ti-indicator.md) Colección|Enumerar [entidades de](ti-indicator.md) indicador.
[Enviar indicador](post-ti-indicator.md)|[Indicador](ti-indicator.md)|Enviar o actualizar entidad [Indicator.](ti-indicator.md)
[Indicadores de importación](import-ti-indicators.md)|[Indicador](ti-indicator.md) Colección|Enviar o actualizar [entidades de](ti-indicator.md) indicadores.
[Eliminar indicador](delete-ti-indicator-by-id.md)|Sin contenido|Elimina la [entidad Indicator.](ti-indicator.md)

## <a name="properties"></a>Propiedades

Propiedad|Tipo|Descripción
:---|:---|:---
id|Cadena|Identidad de la [entidad Indicator.](ti-indicator.md)
indicatorValue|Cadena|El valor del [indicador](ti-indicator.md).
indicatorType|Enum|Tipo del indicador. Los valores posibles son: "FileSha1", "FileSha256", "FileMd5", "CertificateThumbprint", "IpAddress", "DomainName" y "Url".
aplicación|Cadena|La aplicación asociada al indicador.
acción|Enum|La acción que se realizará si el indicador se detectará en la organización. Los valores posibles son: "Warn", "Block", "Audit", "Alert", "AlertAndBlock", "BlockAndRemediate" y "Allowed".
|externalID|Cadena|Id que el cliente puede enviar en la solicitud de correlación personalizada.|
sourceType|Enum|"Usuario" en caso de que el indicador creado por un usuario (por ejemplo, desde el portal), "AadApp" en caso de que se haya enviado mediante una aplicación automatizada a través de la API.
createdBySource|string|Nombre del usuario o aplicación que envió el indicador.
createdBy|String|Identidad única del usuario/aplicación que envió el indicador.
lastUpdatedBy|Cadena|Identidad del usuario/aplicación que actualizó por última vez el indicador.
creationTimeDateTimeUtc|DateTimeOffset|La fecha y hora en que se creó el indicador.
expirationTime|DateTimeOffset|La hora de expiración del indicador.
lastUpdateTime|DateTimeOffset|La última vez que se actualizó el indicador.
severity|Enum|Gravedad del indicador. los valores posibles son: "Informational", "Low", "Medium" y "High".
title|Cadena|Título del indicador.
description|Cadena|Descripción del indicador.
recommendedActions|Cadena|Acciones recomendadas para el indicador.
rbacGroupNames|Lista de cadenas|Nombres de grupo de dispositivo RBAC donde se expone y activa el indicador. Lista vacía en caso de que se exponga a todos los dispositivos.
rbacGroupIds|Lista de cadenas|Id. de grupo de dispositivo RBAC donde se expone y activa el indicador. Lista vacía en caso de que se exponga a todos los dispositivos.
## <a name="public-preview-indicator-types"></a>Vista previa pública: tipos de indicador

> [!IMPORTANT]
> La información de esta sección (**Public Preview for Automated investigation and remediation engine**) se relaciona con el producto preinstalado que podría modificarse considerablemente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Los tipos de acción de indicador admitidos por la API son:

- Permitido
- Alerta
- AlertAndBlock
- Auditoría
- Bloquear
- BlockAndRemediate
- Advertir

La lista de tipos de acción de la API contiene las nuevas acciones de respuesta junto con las acciones de respuesta anteriores (AlertAndBlock y Alert). Para obtener más información sobre la descripción de los tipos de acción de respuesta, vea [Create indicators](manage-indicators.md).

Las acciones de respuesta allowed, Warn, Block y BlockAndRemediate IoC se encuentran en versión preliminar pública. Para obtener más información sobre la vista previa pública, [vea Public Preview: Custom file IoC enhancements and API schema update - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/public-preview-custom-file-ioc-enhancements-and-api-schema/ba-p/2676997).




> [!Note]
>
> Las acciones de respuesta anteriores (AlertAndBlock y Alert) se quitarán cuando la característica haya llegado a GAed. La fecha estimada de ga con período de gracia finaliza en octubre de 2021.  Se recomienda actualizar las plantillas o scripts existentes tan pronto como sea posible.

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
