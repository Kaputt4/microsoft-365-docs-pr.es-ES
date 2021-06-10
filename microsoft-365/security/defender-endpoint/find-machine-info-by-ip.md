---
title: Buscar información del dispositivo por API IP interna
description: Use esta API para crear llamadas relacionadas con la búsqueda de una entrada de dispositivo alrededor de una marca de tiempo específica por IP interna.
keywords: ip, apis, api de gráficos, api admitidas, buscar dispositivo, información del dispositivo
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167144"
---
# <a name="find-device-information-by-internal-ip-api"></a>Buscar información del dispositivo por API IP interna

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Buscar un dispositivo por IP interna.

>[!NOTE]
>La marca de tiempo debe estar dentro de los últimos 30 días.

## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
:---|:---|:---
Aplicación | Machine.Read.All | 'Leer todos los perfiles de máquina'
Aplicación | Machine.ReadWrite.All | 'Leer y escribir toda la información de la máquina'

## <a name="http-request"></a>Solicitud HTTP
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.


## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente y la máquina existe: 200 Aceptar.
Si no se encuentra ninguna máquina: 404 No se encontró.


## <a name="example"></a>Ejemplo:

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.

La respuesta devolverá una lista de todos los dispositivos que informaron de esta dirección IP en los dieciséis minutos antes y después de la marca de tiempo. 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
