---
title: Restringir api de ejecución de aplicaciones
description: Use esta API para crear llamadas relacionadas con la restricción de la ejecución de una aplicación.
keywords: api, api de gráfico, api admitidas, paquete de investigación de recopilación
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
ms.technology: mde
ms.openlocfilehash: 149f3aefd963f15eafa15030a322ec588c0615ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186789"
---
# <a name="restrict-app-execution-api"></a>Restringir api de ejecución de aplicaciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Restringir la ejecución de todas las aplicaciones en el dispositivo excepto un conjunto predefinido.


## <a name="limitations"></a>Limitaciones
1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   Machine.RestrictExecution | 'Restringir la ejecución de código'
Delegado (cuenta profesional o educativa) | Machine.RestrictExecution | 'Restringir la ejecución de código'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
>- El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)

## <a name="http-request"></a>Solicitud HTTP
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.
Content-Type | string | application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud
En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro | Tipo    | Descripción
:---|:---|:---
Comentario |   Cadena |    Comentario para asociarlo a la acción. **Necesario**.

## <a name="response"></a>Respuesta
Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.


## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- Para quitar la restricción de ejecución de código de un dispositivo, consulta [Quitar restricción de aplicación.](unrestrict-code-execution.md)
