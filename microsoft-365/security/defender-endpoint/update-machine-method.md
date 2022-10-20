---
title: Actualización de la API de entidad de máquina
description: Obtenga información sobre cómo actualizar las etiquetas de máquina mediante esta API. Puede actualizar las etiquetas y las propiedades devicevalue.
keywords: apis, graph api, api admitidas, get, alert, information, id
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 640a5ec91fbfefe674f692e29ef9544dc54f14e1
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644240"
---
# <a name="update-machine"></a>Actualizar máquina 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Novedades propiedades de [la máquina](machine.md) existente.

Las propiedades actualizables son: `machineTags` y `deviceValue`.

## <a name="limitations"></a>Limitaciones

1. Puede actualizar las máquinas que están disponibles en la API. 
2. La máquina de actualización solo anexa etiquetas a la colección de etiquetas. Si existen etiquetas, deben incluirse en la colección de etiquetas del cuerpo.
3. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Machine.ReadWrite.All|"Leer y escribir información de máquina para todas las máquinas"
Delegado (cuenta profesional o educativa)|Machine.ReadWrite|"Leer y escribir información de la máquina"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
> - El usuario debe tener al menos el siguiente permiso de rol: "Investigación de alertas". Para obtener más información, consulte [Creación y administración de roles](user-roles.md).
> - El usuario debe tener acceso al dispositivo asociado a la alerta, en función de la configuración del grupo de dispositivos. Para obtener más información, consulte [Creación y administración de grupos de dispositivos](machine-groups.md).
>
> La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión.

## <a name="http-request"></a>Solicitud HTTP

```http
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|Cadena|application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En el cuerpo de la solicitud, proporcione los valores de los campos pertinentes que se deben actualizar.

Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad.

Para obtener el mejor rendimiento, no debe incluir valores existentes que no hayan cambiado.

Propiedad|Tipo|Descripción
:---|:---|:---
machineTags|Colección de cadenas|Conjunto de etiquetas de [máquina](machine.md) .
deviceValue|Enumeración que acepta valores NULL|[Valor del dispositivo](tvm-assign-device-value.md). Los valores posibles son: "Normal", "Low" y "High".

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK y la entidad [de máquina](machine.md) en el cuerpo de la respuesta con las propiedades actualizadas.

Si la colección de etiquetas de máquina en el cuerpo no contiene etiquetas de máquina existentes, reemplaza todas las etiquetas por las etiquetas proporcionadas en el cuerpo de la solicitud.

Si no se encontró la máquina con el identificador especificado: 404 No encontrado.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Este es un ejemplo de la solicitud.

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10" "Windows11",
                     "Windows Insider - Fast"
    ]
}
```
