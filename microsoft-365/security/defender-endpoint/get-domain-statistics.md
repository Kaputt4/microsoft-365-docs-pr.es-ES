---
title: Obtención de la API de estadísticas de dominio
description: Obtenga información sobre cómo usar la API Get domain statistics para recuperar las estadísticas del dominio determinado en Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, get, domain, domain related devices
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: e4dc4137525f9f3019f98979ef33a219868ed15b
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67523674"
---
# <a name="get-domain-statistics-api"></a>Obtención de la API de estadísticas de dominio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera las estadísticas del dominio determinado.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.
2. El valor máximo de `lookbackhours` es 720 horas (30 días).

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Url. Read.All|"Leer direcciones URL"
Delegado (cuenta profesional o educativa)|Url. Read.All|"Leer direcciones URL"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado|Valor
:---|:---
Authorization|Portador {token}. **Necesario**.

## <a name="request-uri-parameters"></a>Parámetros de URI de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
lookBackHours|Int32|Define las horas que se buscan para obtener las estadísticas. El valor predeterminado es 30 días. **Opcional**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si es correcto y el dominio existe: 200 Correcto, con el objeto de estadísticas en el cuerpo de la respuesta. Si el dominio no existe: 200 Correcto con una prevalencia establecida en 0.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
