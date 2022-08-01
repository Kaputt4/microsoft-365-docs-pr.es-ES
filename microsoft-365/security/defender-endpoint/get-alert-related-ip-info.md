---
title: Obtener información de ip relacionadas con alertas
description: Recupera todas las IP relacionadas con una alerta específica mediante Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api compatibles, obtener información de alerta, información de alertas, ip relacionada
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
ms.openlocfilehash: 00761e07dd0018236e58aaa5a36efec0cc16ebd5
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168215"
---
# <a name="get-alert-related-ips-information-api"></a>Obtener la API de información de ip relacionadas con alertas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera todas las IP relacionadas con una alerta específica.

## <a name="limitations"></a>Limitaciones

1. Puede consultar las alertas actualizadas por última vez de acuerdo con el período de retención configurado.
2. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Ip.Read.All|'Leer perfiles de dirección IP'
Delegado (cuenta profesional o educativa)|Ip.Read.All|'Leer perfiles de dirección IP'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (Para obtener más información, vea [Crear y administrar roles](user-roles.md))
> - El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (Para obtener más información, vea [Crear y administrar grupos de dispositivos](machine-groups.md))

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente y se alerta y existe una IP: 200 Aceptar. Si no se encuentra la alerta: 404 No se encontró.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Este es un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

### <a name="response-example"></a>Ejemplo de respuesta

Este es un ejemplo de la respuesta:

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228
                }
                ...
    ]
}
```
