---
title: Obtener API de incidentes
description: Obtenga información sobre cómo usar la API Obtener incidentes para obtener un único incidente en Microsoft 365 Defender.
keywords: apis, api de gráficos, api admitidas, get, file, hash
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
ms.openlocfilehash: 1e50e997dd6a64ac20b06c4a2717f10716642607c815dc12a9732dd64a419c93
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53888840"
---
# <a name="get-incident-information-api"></a>Obtener API de información de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera un incidente específico por su identificador

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API.

Tipo de permiso|Permiso|Nombre para mostrar de permisos
---|---|---
Aplicación|Incident.Read.All|'Leer todos los incidentes'
Aplicación|Incident.ReadWrite.All|'Leer y escribir todos los incidentes'
Delegado (cuenta profesional o educativa)|Incident.Read|'Leer incidentes'
Delegado (cuenta profesional o educativa)|Incident.ReadWrite|'Leer y escribir incidentes'

> [!NOTE]
>
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: 'Ver datos'
> - La respuesta solo incluirá incidentes a los que el usuario esté expuesto

## <a name="http-request"></a>Solicitud HTTP

```console
GET .../api/incidents/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
---|---|---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200 Ok y la entidad incident en el cuerpo de la respuesta.
Si no se encontró un incidente con el identificador especificado: 404 No encontrado.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
