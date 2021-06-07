---
title: Obtener api de máquina por id.
description: Obtén información sobre cómo usar la API Obtener máquina por id. para recuperar una máquina por su id. de dispositivo o nombre de equipo en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, dispositivos, entidad, id
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: e4ed5a68b0f4c5e9472702d3cc2798a810e4f84e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769478"
---
# <a name="get-machine-by-id-api"></a>Obtener api de máquina por id.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)


> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Recupera un equipo [específico por](machine.md) su identificador de dispositivo o el nombre del equipo.


## <a name="limitations"></a>Limitaciones
1. Puedes obtener dispositivos vistos por última vez de acuerdo con la directiva de retención configurada.
2. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   Machine.Read.All |  'Leer todos los perfiles de máquina'
Aplicación |   Machine.ReadWrite.All | 'Leer y escribir toda la información de la máquina'
Delegado (cuenta profesional o educativa) | Machine.Read | 'Leer información de máquina'
Delegado (cuenta profesional o educativa) | Machine.ReadWrite | 'Leer y escribir información de máquina'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
>- El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)


## <a name="http-request"></a>Solicitud HTTP
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.


## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente y el dispositivo existe: 200 Aceptar con la [entidad de la](machine.md) máquina en el cuerpo.
Si no se encontró el equipo con el identificador especificado: 404 No se encontró.


## <a name="example"></a>Ejemplo:

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2018-08-02T14:55:03.7791856Z",
    "osPlatform": "Windows10",
    "version": "1709",
    "osProcessor": "x64",
    "lastIpAddress": "172.17.230.209",
    "lastExternalIpAddress": "167.220.196.71",
    "osBuild": 18209,
    "healthStatus": "Active",
    "rbacGroupId": 140,
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Medium",
    "isAadJoined": true,
    "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
    "machineTags": [ "test tag 1", "test tag 2" ]
}

```
