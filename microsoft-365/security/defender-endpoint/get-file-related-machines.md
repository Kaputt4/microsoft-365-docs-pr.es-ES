---
title: Api de obtención de máquinas relacionadas con archivos
description: Obtenga información sobre cómo usar la API Obtener máquinas relacionadas con archivos para obtener una colección de máquinas relacionadas con un hash de archivo en Microsoft Defender para punto de conexión.
keywords: api, graph api, api admitidas, get, devices, hash
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
ms.openlocfilehash: 9b4382b3ec77ecaa272ddf3e56dd77442fbe4fe6
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326021"
---
# <a name="get-file-related-machines-api"></a>Api de obtención de máquinas relacionadas con archivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera una colección de [máquinas](machine.md) relacionadas con un hash de archivo determinado.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.
2. Solo se admite la función hash SHA-1 (no MD5 o SHA-256).

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

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
> - La respuesta incluirá solo dispositivos a los que el usuario tenga acceso, en función de la configuración del grupo de dispositivos (consulte [Creación y administración de grupos de dispositivos](machine-groups.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/files/{id}/machines
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si es correcto y el archivo existe: 200 Aceptar con la lista de entidades de [máquina](machine.md) en el cuerpo. Si el archivo no existe: 200 Aceptar con un conjunto vacío.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
