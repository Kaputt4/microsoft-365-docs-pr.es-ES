---
title: Obtención de la API de estadísticas ip
description: Obtenga las estadísticas más recientes de la dirección IP mediante Microsoft Defender para punto de conexión.
keywords: api, graph api, api admitidas, get, ip, estadísticas, prevalencia
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
ms.openlocfilehash: aacc37a64890d045e165b9a4eb4bba317afea9f0
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68192935"
---
# <a name="get-ip-statistics-api"></a>Obtención de la API de estadísticas ip

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API
Recupera las estadísticas de la dirección IP especificada.

## <a name="limitations"></a>Limitaciones
1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.
2. El valor máximo de Lookbackhours es 720 Horas (30 días).

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Ip.Read.All|"Leer perfiles de dirección IP"
Delegado (cuenta profesional o educativa)|Ip.Read.All|"Leer perfiles de dirección IP"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-uri-parameters"></a>Parámetros de URI de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
lookBackHours|Int32|Define las horas que se buscan para obtener las estadísticas. El valor predeterminado es 30 días. **Opcional**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente e ip existe: 200 Correcto con datos estadísticos en el cuerpo. La dirección IP es válida, pero no existe: organizationPrevalence 0, IP no es válida: HTTP 400.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```

|Nombre|Descripción|
|---|---|
|Prevalencia de la organización|el número distinto de dispositivos que abrieron la conexión de red a esta dirección IP.|
|Organización vista por primera vez|la primera conexión para esta dirección IP en la organización.|
|Organización vista por última vez|la última conexión para esta dirección IP en la organización.|

> [!NOTE]
> Esta información estadística se basa en los datos de los últimos 30 días.
