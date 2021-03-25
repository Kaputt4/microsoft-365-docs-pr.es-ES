---
title: ESTABLECER API de valor de dispositivo
description: Obtén información sobre cómo especificar el valor de un dispositivo mediante una API de Microsoft Defender para endpoints.
keywords: apis, api de gráficos, api admitidas, etiquetas, etiquetas de máquina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33692ddf62153c0a6aa8f84568d69803af113bc6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185568"
---
# <a name="set-device-value-api"></a>ESTABLECER API de valor de dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API

Establece el valor de dispositivo de un [equipo específico.](machine.md)<br>
Consulta [Asignar valores de dispositivo](tvm-assign-device-value.md) para obtener más información.

## <a name="limitations"></a>Limitaciones

1. Puedes publicar en dispositivos vistos por última vez según el período de retención configurado.

2. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |    Permiso    |    Nombre para mostrar de permisos
:---|:---|:---
Aplicación |    Machine.ReadWrite.All |    'Leer y escribir toda la información de la máquina'
Delegado (cuenta profesional o educativa) | Machine.ReadWrite | 'Leer y escribir información de máquina'

>[!Note]
> Al obtener un token con credenciales de usuario:
>
>- El usuario debe tener al menos el siguiente permiso de función: "Administrar la configuración de seguridad". Para obtener más información (vea [Crear y administrar roles](user-roles.md) para obtener más información)
>- El usuario debe tener acceso a la máquina en función de la configuración del grupo de máquinas (vea [Crear y](machine-groups.md) administrar grupos de máquinas para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.
Content-Type | string | application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro |    Tipo    | Descripción
:---|:---|:---
DeviceValue |    Enum |    Valor del dispositivo. Los valores permitidos son: 'Normal', 'Low' y 'High'. **Necesario**.

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200: código de respuesta Aceptar y la máquina actualizada en el cuerpo de la respuesta.

## <a name="example"></a>Ejemplo

**Solicitud**

Este es un ejemplo de una solicitud que agrega etiqueta de máquina.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
