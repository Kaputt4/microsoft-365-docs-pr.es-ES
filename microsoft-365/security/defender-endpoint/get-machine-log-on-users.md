---
title: Obtención de la API de usuarios de inicio de sesión de la máquina
description: Obtenga información sobre cómo usar la API Obtener usuarios de inicio de sesión de máquina para recuperar una colección de usuarios que han iniciado sesión en un dispositivo en Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, get, device, log on, users
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
ms.openlocfilehash: 7c397496c635f2a4501506fa555d9a4f03b78766
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67524224"
---
# <a name="get-machine-logon-users-api"></a>Obtención de la API de usuarios de inicio de sesión de la máquina

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Recupera una colección de usuarios que han iniciado sesión en un dispositivo específico.

## <a name="limitations"></a>Limitaciones
1. Puede consultar las alertas actualizadas por última vez según el período de retención configurado.
2. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application |User.Read.All |"Leer perfiles de usuario"
Delegado (cuenta profesional o educativa) | User.Read.All | "Leer perfiles de usuario"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos". Para obtener más información, consulte [Creación y administración de roles](user-roles.md).
> - La respuesta incluirá usuarios solo si el dispositivo es visible para el usuario, en función de la configuración del grupo de dispositivos. Para obtener más información, consulte [Creación y administración de grupos de dispositivos](machine-groups.md).

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si es correcto y el dispositivo existe: 200 Aceptar con la lista de entidades de [usuario](user.md) en el cuerpo. Si no se encontró el dispositivo: 404 No encontrado.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a>Respuesta

Aquí tiene un ejemplo de la respuesta.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
