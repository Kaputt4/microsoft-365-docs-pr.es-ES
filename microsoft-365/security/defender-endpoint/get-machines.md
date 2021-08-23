---
title: ENUMERAR API de máquinas
description: Obtenga información sobre cómo usar la API enumerar máquinas para recuperar una colección de máquinas que se han comunicado con Microsoft Defender para la nube de puntos de conexión.
keywords: api, api de gráfico, api admitidas, get, dispositivos
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
ms.topic: article
ms.collection: M365-security-compliance
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8ffeca3d13b42e39f539e96d563aceabd464aeaf
ms.sourcegitcommit: be83f1222c30ffa8202c19a2797cc755fc3b72af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2021
ms.locfileid: "58372462"
---
# <a name="list-machines-api"></a>ENUMERAR API de máquinas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera una colección de [máquinas](machine.md) que se han comunicado con Microsoft Defender para la nube de extremo.

Admite [consultas de OData V4](https://www.odata.org/documentation/).

La consulta de OData `$filter` se admite en: `computerDnsName` , , , , , , , `id` , y `version` `deviceValue` `aadDeviceId` `machineTags` `lastSeen` `exposureLevel` `lastIpAddress` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .
<br>```$stop``` con un valor máximo de 10 000
<br>```$skip``` Vea ejemplos en [consultas de OData con Defender para endpoint](exposed-apis-odata-samples.md)

## <a name="limitations"></a>Limitaciones

1. Puedes obtener dispositivos vistos por última vez según el período de retención configurado.
2. El tamaño máximo de página es 10.000.
3. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora. 

## <a name="permissions"></a>Permisos

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Machine.Read.All|'Leer todos los perfiles de máquina'
Aplicación|Machine.ReadWrite.All|'Leer y escribir toda la información de la máquina'
Delegado (cuenta profesional o educativa)|Machine.Read|'Leer información de máquina'
Delegado (cuenta profesional o educativa)|Machine.ReadWrite|'Leer y escribir información de máquina'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
> - La respuesta incluirá solo dispositivos a los que el usuario tenga acceso, en función de la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente y las máquinas existen: 200 Aceptar con una lista [de](machine.md) entidades de máquina en el cuerpo. Si no hay máquinas recientes: 404 No se encontró.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
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
        ...
    ]
}
```

## <a name="related-topics"></a>Temas relacionados

- [Consultas de OData con Microsoft Defender para endpoint](exposed-apis-odata-samples.md)
