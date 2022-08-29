---
title: Api de objeto Get MachineAction
description: Obtenga información sobre cómo usar la API Get MachineAction para recuperar una acción de máquina específica mediante su identificador en Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, machineaction (objeto)
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 4fa508be9abdbf0f589b1dd488d905386c42a183
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326945"
---
# <a name="get-machineaction-api"></a>Obtención de machineAction API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera [una acción de máquina](machineaction.md) específica por su identificador.

## <a name="limitations"></a>Limitaciones

- Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Defender para API de punto de conexión](apis-intro.md).

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Machine.Read.All|"Leer todos los perfiles de máquina"
Application|Machine.ReadWrite.All|"Leer y escribir toda la información de la máquina"
Delegado (cuenta profesional o educativa)|Machine.Read|"Leer información de la máquina"
Delegado (cuenta profesional o educativa)|Machine.ReadWrite|"Leer y escribir información de la máquina"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve el código de respuesta 200, Ok con una entidad [Machine Action](machineaction.md) . Si no se encontró la entidad de acción de máquina con el identificador especificado: 404 No encontrado.

## <a name="example"></a>Ejemplo

### <a name="example-request"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

### <a name="response-example"></a>Ejemplo de respuesta

Este es un ejemplo de la respuesta:

```json
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}
```
