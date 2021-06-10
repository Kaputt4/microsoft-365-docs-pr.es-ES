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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/07/2018
ms.openlocfilehash: 18566025d79f02281c1d2c1509dd98f1e57879c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932780"
---
# <a name="get-kb-collection-api"></a>Obtener API de colección KB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Recupera una colección de grupos de dispositivos RBAC.

## <a name="permissions"></a>Permisos
El usuario necesita permisos de lectura.

## <a name="http-request"></a>Solicitud HTTP
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado | Valor 
:---|:---
Authorization | Portador {token}. **Necesario**.
Tipo de contenido | application/json

## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente: 200 Aceptar.

## <a name="example"></a>Ejemplo:

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.
El identificador de campo contiene el identificador de **grupo de** dispositivos y es igual al **campo rbacGroupId** en la información de dispositivos. El **campo desagrupado** solo se aplica a un grupo para todos los dispositivos que no se han asignado a ningún grupo. Este grupo, como siempre, tiene el nombre "UnassignedGroup".

```
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
        …
}
```
