---
title: Actualizar API de entidad de máquina
description: Obtenga información sobre cómo actualizar las etiquetas de máquina mediante esta API. Puedes actualizar las etiquetas y las propiedades devicevalue.
keywords: apis, api de gráficos, api admitidas, get, alert, information, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985748"
---
# <a name="update-machine"></a>Actualizar máquina 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Actualiza las propiedades [de](machine.md)machine existente .
<br>Las propiedades actualizables son: ```machineTags``` y ```deviceValue``` .


## <a name="limitations"></a>Limitaciones
1. Puede actualizar las máquinas que están disponibles en la API. 
2. La máquina de actualización solo anexa etiquetas a la colección de etiquetas. Si existen etiquetas, deben incluirse en la colección de etiquetas del cuerpo.
3. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   Machine.ReadWrite.All | 'Leer y escribir información de máquina para todas las máquinas'
Delegado (cuenta profesional o educativa) | Machine.ReadWrite | 'Leer y escribir información de máquina'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas". Para obtener más información, vea [Create and manage roles](user-roles.md).
>- El usuario debe tener acceso al dispositivo asociado con la alerta, en función de la configuración del grupo de dispositivos. Para obtener más información, consulta [Crear y administrar grupos de dispositivos.](machine-groups.md)

## <a name="http-request"></a>Solicitud HTTP
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | String | Portador {token}. **Necesario**.
Content-Type | Cadena | application/json. **Necesario**.


## <a name="request-body"></a>Cuerpo de solicitud
En el cuerpo de la solicitud, proporcione los valores de los campos relevantes que deben actualizarse.
<br>Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad. 
<br>Para obtener el mejor rendimiento, no debe incluir valores existentes que no hayan cambiado.

Propiedad | Tipo | Descripción
:---|:---|:---
machineTags | Colección de cadenas | Conjunto de [etiquetas de](machine.md) máquina.
deviceValue | Enumeración que admite valores null | El [valor del dispositivo](tvm-assign-device-value.md). Los valores posibles son: 'Normal', 'Low' y 'High'.

## <a name="response"></a>Respuesta
Si se realiza correctamente, este método devuelve 200 Ok y la entidad [de](machine.md) la máquina en el cuerpo de la respuesta con las propiedades actualizadas. Si la colección de etiquetas de máquina en el cuerpo no contiene etiquetas de máquina existentes: 400 Entradas no válidas y un mensaje que informa de las etiquetas que faltan.
Si no se encontró el equipo con el identificador especificado: 404 No se encontró.


## <a name="example"></a>Ejemplo

**Solicitud**

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
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
