---
title: Cancelar API de acción de máquina
description: Obtenga información sobre cómo cancelar una acción de máquina iniciada ya
keywords: apis, api de gráficos,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879801"
---
#   <a name="cancel-machine-action-api"></a>Cancelar API de acción de máquina 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Cancelar una acción de máquina ya iniciada que aún no está en estado final (completada, cancelada, fallida).

## <a name="limitations"></a>Limitaciones

1.  Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, vea [Get started](apis-intro.md).

|     Tipo de permiso     |     Permiso     |    Nombre para mostrar de permisos     |
|-|-|-|
|    <br>Aplicación    |    <br>Machine.CollectForensic<br>   Machine.Isolate   <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantine<br>   Machine.LiveResponse    |    Recopilar forenses   <br>Aislar máquina<br>Restringir la ejecución de código<br>  Máquina de digitalización<br>  Máquina offboard<br>   Detener y poner en cuarentena<br>   Ejecutar respuesta en directo en un equipo específico    |
|    <br>Delegado (cuenta de trabajo o escuela)    |    Machine.CollectForensic<br>   Machine.Isolate    <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantineMachine.LiveResponse    |    Recopilar forenses<br>   Aislar máquina<br>  Restringir la ejecución de código<br> Máquina de digitalización<br>Máquina offboard<br> Detener y poner en cuarentena<br> Ejecutar respuesta en directo en un equipo específico    |


## <a name="http-request"></a>Solicitud HTTP

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a>Encabezados de solicitud

| Nombre      | Tipo | Descripción                 |
|---------------|----------|---------------------------------|
| Authorization | Cadena   | {token} de portador. Obligatorio.   |
| Content-Type  | string   | application/json. Obligatorio. |

## <a name="request-body"></a>Cuerpo de la solicitud

| Parámetro | Tipo | Description                        |
|---------------|----------|----------------------------------------|
| Comentario       | Cadena   | Comentario para asociarlo con la acción de cancelación.  |

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200, código de respuesta Ok con una entidad Machine Action. Si no se encontró la entidad de acción de la máquina con el identificador especificado: 404 No encontrado.

## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>Tema relacionado

- [Obtener API de acción de máquina](get-machineaction-object.md)