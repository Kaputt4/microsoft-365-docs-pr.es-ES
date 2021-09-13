---
title: Obtener API de máquinas relacionadas con archivos
description: Obtenga información sobre cómo usar la API Obtener máquinas relacionadas con archivos para obtener una colección de máquinas relacionadas con un hash de archivo en Microsoft Defender para endpoint.
keywords: api, api de gráfico, api admitidas, get, dispositivos, hash
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
ms.openlocfilehash: 722c4a28ab477b34fc3e52cb3eb3efddf319d0d8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221402"
---
# <a name="get-file-related-machines-api"></a>Obtener API de máquinas relacionadas con archivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera una colección de [máquinas relacionadas](machine.md) con un hash de archivo determinado.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.
2. Solo se admite la función hash SHA-1 (no MD5 ni SHA-256).

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Machine.Read.All|'Leer todos los perfiles de máquina'
Aplicación|Machine.ReadWrite.All|'Leer y escribir toda la información de la máquina'
Delegado (cuenta profesional o educativa)|Machine.Read|'Leer información de máquina'
Delegado (cuenta profesional o educativa)|Machine.ReadWrite|'Leer y escribir información de máquina'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
> - La respuesta incluirá solo dispositivos a los que el usuario tenga acceso, en función de la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/files/{id}/machines
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente y el archivo existe: 200 Aceptar con la lista [de](machine.md) entidades de máquina en el cuerpo. Si el archivo no existe: 200 Aceptar con un conjunto vacío.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
