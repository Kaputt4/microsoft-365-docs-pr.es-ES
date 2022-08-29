---
title: Cancelación de la API de acción de la máquina
description: Obtenga información sobre cómo cancelar una acción de máquina ya iniciada
keywords: apis, graph api,
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: d5736ee3374b182f1b22f1b728ac2378eb66b66d
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331893"
---
# <a name="cancel-machine-action-api"></a>Cancelación de la API de acción de la máquina

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/defender-endpoint)
- [Microsoft Defender para punto de conexión Plan 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Cancele una acción de máquina ya iniciada que aún no esté en estado final (completada, cancelada, con errores).

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Introducción](apis-intro.md).

|Tipo de permiso|Permiso|Nombre para mostrar del permiso|
|---|---|---|
|Application|Machine.CollectForensics <br> Machine.Isolate <br> Machine.RestrictExecution <br> Machine.Scan <br> Machine.Offboard <br> Machine.StopAndQuarantine <br> Machine.LiveResponse|Recopilación de forenses <br>Aislar máquina<br>Restringir la ejecución del código<br>  Equipo de examen<br>  Retirar la máquina<br> Detener y poner en cuarentena<br> Ejecución de una respuesta en directo en una máquina específica|
|Delegado (cuenta profesional o educativa)|Machine.CollectForensics<br> Machine.Isolate  <br>Machine.RestrictExecution<br> Machine.Scan<br> Machine.Offboard<br> Machine.StopAndQuarantineMachine.LiveResponse|Recopilación de forenses<br> Aislar máquina<br>  Restringir la ejecución del código<br> Equipo de examen<br>Retirar la máquina<br> Detener y poner en cuarentena<br> Ejecución de una respuesta en directo en una máquina específica|

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel
```

## <a name="request-headers"></a>Encabezados de solicitud

|Nombre|Tipo|Descripción|
|---|---|---|
|Authorization|Cadena|{token} de portador. Obligatorio.|
|Content-Type|string|application/json. Obligatorio.|

## <a name="request-body"></a>Cuerpo de solicitud

|Parámetro|Tipo|Descripción|
|---|---|---|
|Comentario|Cadena|Comentario que se va a asociar a la acción de cancelación.|

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve el código de respuesta 200, OK con una entidad Machine Action. Si no se encontró la entidad de acción de máquina con el identificador especificado: 404 No encontrado.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

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

- [Obtención de la API de acción de la máquina](get-machineaction-object.md)
