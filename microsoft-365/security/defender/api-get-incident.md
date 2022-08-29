---
title: Obtención de la API de incidentes
description: Obtenga información sobre cómo usar la API Get incidents para obtener un único incidente en Microsoft 365 Defender.
keywords: api, graph api, api admitidas, get, file, hash
search.product: eADQiWindows 10XVcnh
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
MS.technology: m365d
ms.custom: api
ms.openlocfilehash: af54daf82ca8f4fbd50c5aaeafd4482f2ce6b0ca
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67329099"
---
# <a name="get-incident-information-api"></a>Obtención de la API de información de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera un incidente específico por su identificador

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API.

Tipo de permiso|Permiso|Nombre para mostrar del permiso
---|---|---
Application|Incident.Read.All|"Leer todos los incidentes"
Application|Incident.ReadWrite.All|"Leer y escribir todos los incidentes"
Delegado (cuenta profesional o educativa)|Incident.Read|"Leer incidentes"
Delegado (cuenta profesional o educativa)|Incident.ReadWrite|"Incidentes de lectura y escritura"

> [!NOTE]
>
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos".
> - La respuesta solo incluirá los incidentes a los que está expuesto el usuario.

## <a name="http-request"></a>Solicitud HTTP

```console
GET .../api/incidents/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
---|---|---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK y la entidad incident en el cuerpo de la respuesta.
Si no se encontró el incidente con el identificador especificado: 404 No encontrado.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
