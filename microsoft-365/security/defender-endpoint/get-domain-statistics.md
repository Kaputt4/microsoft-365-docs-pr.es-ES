---
title: Obtener API de estadísticas de dominio
description: Obtenga información sobre cómo usar la API Obtener estadísticas de dominio para recuperar las estadísticas del dominio especificado en Microsoft Defender para endpoint.
keywords: api, api de gráfico, api admitidas, obtener, dominio, dispositivos relacionados con el dominio
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
ms.openlocfilehash: 50b05b98ba507e120bbd6a3dc09f4633dac3a005
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998781"
---
# <a name="get-domain-statistics-api"></a>Obtener API de estadísticas de dominio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Recupera las estadísticas del dominio determinado.


## <a name="limitations"></a>Limitaciones
1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   DIRECCIÓN URL. Read.All |  'Leer direcciones URL'
Delegado (cuenta profesional o educativa) | DIRECCIÓN URL. Read.All | 'Leer direcciones URL'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)

## <a name="http-request"></a>Solicitud HTTP
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado | Valor 
:---|:---
Authorization | Portador {token}. **Necesario**.

## <a name="request-uri-parameters"></a>Parámetros uri de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
lookBackHours | Int32 | Define las horas que buscamos para obtener las estadísticas. El valor predeterminado es 30 días. **Opcional**.

## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente y el dominio existe: 200 Ok, con el objeto statistics en el cuerpo de la respuesta. Si el dominio no existe: 404 No encontrado.


## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

**Respuesta**

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
