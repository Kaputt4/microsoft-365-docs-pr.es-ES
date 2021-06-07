---
title: Buscar dispositivos por API IP interna
description: Buscar dispositivos vistos con la IP interna solicitada en el intervalo de tiempo de 15 minutos antes y después de una marca de tiempo determinada
keywords: apis, api de gráfico, api admitidas, get, device, IP, find, find device, by ip, ip
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
ms.openlocfilehash: 46afa945ce86c35e3af1c542eb1a9770041b3430
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769442"
---
# <a name="find-devices-by-internal-ip-api"></a>Buscar dispositivos por API IP interna

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Buscar [máquinas](machine.md) vistas con la IP interna solicitada en el intervalo de tiempo de 15 minutos antes y después de una marca de tiempo determinada.


## <a name="limitations"></a>Limitaciones
1. La marca de tiempo especificada debe estar en los últimos 30 días.
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
> - La respuesta incluirá solo los dispositivos a los que el usuario tenga acceso en función de la configuración del grupo de dispositivos (consulta [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)
> - El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
> - La respuesta incluirá solo los dispositivos a los que el usuario tenga acceso en función de la configuración del grupo de dispositivos (consulta [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)

## <a name="http-request"></a>Solicitud HTTP
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente: 200 Aceptar con una lista de las máquinas en el cuerpo de la respuesta.
Si la marca de tiempo no está en los últimos 30 días: 400 solicitudes no válidas.

## <a name="example"></a>Ejemplo:

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
