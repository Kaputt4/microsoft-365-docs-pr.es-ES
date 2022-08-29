---
title: API de investigaciones de lista
description: Uso de esta API para crear llamadas relacionadas con la obtención de la colección Investigations
keywords: apis, graph api, api admitidas, colección Investigations
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
ms.openlocfilehash: 746cf78bce54651cc24dd07a90c5fc11772903d2
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67325999"
---
# <a name="list-investigations-api"></a>API de investigaciones de lista

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera una colección de [investigaciones](investigation.md).

Admite [consultas de OData V4](https://www.odata.org/documentation/).

La consulta de `$filter` OData se admite en las propiedades : `startTime`, `id`, `machineId` `state`y `triggeringAlertId` .
<br>```$stop``` con un valor máximo de 10 000
<br>```$skip```

Vea ejemplos en [consultas de OData con Microsoft Defender para punto de conexión](exposed-apis-odata-samples.md)

## <a name="limitations"></a>Limitaciones

1. El tamaño máximo de página es de 10 000.
2. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Alert.Read.All|"Leer todas las alertas"
Application|Alert.ReadWrite.All|"Leer y escribir todas las alertas"
Delegado (cuenta profesional o educativa)|Alert.Read|"Leer alertas"
Delegado (cuenta profesional o educativa)|Alert.ReadWrite|"Alertas de lectura y escritura"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve el código de respuesta 200, Ok con una colección de entidades [Investigations](investigation.md) .

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Este es un ejemplo de una solicitud para obtener todas las investigaciones:

```http
GET https://api.securitycenter.microsoft.com/api/investigations
```

### <a name="response-example"></a>Ejemplo de respuesta

Este es un ejemplo de la respuesta:

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
