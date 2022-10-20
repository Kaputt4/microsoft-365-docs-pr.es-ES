---
title: Obtener la API de máquinas relacionadas con el dominio
description: Obtenga información sobre cómo usar la API Get domain-related machines (Obtener máquinas relacionadas con el dominio) para obtener máquinas que se comunicaron con o desde un dominio en Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, get, domain, related, devices
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 1bb28ed69e155bf49f138c5b984cb738d1703c31
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68638134"
---
# <a name="get-domain-related-machines-api"></a>Obtener la API de máquinas relacionadas con el dominio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera una colección de [máquinas](machine.md) que se han comunicado con o desde una dirección de dominio determinada.

## <a name="limitations"></a>Limitaciones

1. Puede consultar en los dispositivos actualizados por última vez según el período de retención configurado.
2. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

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
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos" (para obtener más información, consulte [Creación y administración de roles](user-roles.md)
> - La respuesta incluirá solo los dispositivos a los que el usuario puede acceder, en función de la configuración del grupo de dispositivos (para obtener más información, consulte [Creación y administración de grupos de dispositivos](machine-groups.md)).
>
> La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión.

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente y el dominio existe: 200 Aceptar con la lista de entidades de [máquina](machine.md) . Si el dominio no existe: 200 Aceptar con un conjunto vacío.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Este es un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
