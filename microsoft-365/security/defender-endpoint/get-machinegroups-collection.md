---
title: Obtener LA API de recopilación de grupos de máquinas RBAC
description: Obtenga información sobre cómo usar la API de la colección Get KB para recuperar una colección de grupos de dispositivos RBAC en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, RBAC, group
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/07/2018
ms.custom: api
ms.openlocfilehash: 699a7e2738f1e0c89977bd152832f45935a06387
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167483"
---
# <a name="get-kb-collection-api"></a>Obtener API de colección KB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** 
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera una colección de grupos de dispositivos RBAC.

## <a name="permissions"></a>Permissions

El usuario necesita permisos de lectura.

## <a name="http-request"></a>Solicitud HTTP

```http
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado|Valor
:---|:---
Authorization | Portador {token}. **Necesario**.
Tipo de contenido | application/json

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente: 200 Aceptar.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.
El identificador de campo contiene el identificador de **grupo de** dispositivos y es igual al **campo rbacGroupId** en la información de dispositivos.
El **campo desagrupado** solo se aplica a un grupo para todos los dispositivos que no se han asignado a ningún grupo. Este grupo, como siempre, tiene el nombre "UnassignedGroup".

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        ...
}
```
