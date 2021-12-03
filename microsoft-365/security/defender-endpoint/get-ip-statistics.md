---
title: Obtener API de estadísticas IP
description: Obtén las estadísticas más recientes de tu IP con Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api compatibles, get, ip, statistics, prevalence
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
ms.openlocfilehash: a98b78e85956d49c3b7d7e389882e017dcede3a4
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283261"
---
# <a name="get-ip-statistics-api"></a>Obtener API de estadísticas IP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API
Recupera las estadísticas de la DIRECCIÓN IP determinada.

## <a name="limitations"></a>Limitaciones
1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.
2. El valor máximo de lookbackhours es 720 horas (30 días).

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Ip.Read.All|'Leer perfiles de dirección IP'
Delegado (cuenta profesional o educativa)|Ip.Read.All|'Leer perfiles de dirección IP'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
> - El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-uri-parameters"></a>Parámetros uri de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
lookBackHours|Int32|Define las horas que buscamos para obtener las estadísticas. El valor predeterminado es 30 días. **Opcional**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente e ip existe: 200 Aceptar con datos estadísticos en el cuerpo. Ip es válida pero no existe - organizationPrevalence 0, IP no es válida - HTTP 400.

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
|Prevalencia de la organización|el recuento distinto de dispositivos que abrieron la conexión de red a esta IP.|
|Org first seen|la primera conexión para esta IP en la organización.|
|Org last seen|la última conexión para esta IP en la organización.|

> [!NOTE]
> Esta información estadística se basa en datos de los últimos 30 días.
