---
title: Obtención de la API de máquinas relacionadas con el usuario
description: Obtenga información sobre cómo usar la API Obtener máquinas relacionadas con el usuario para recuperar una colección de dispositivos relacionados con un identificador de usuario en Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, get, user, user related alerts
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: fddef873ffa7cbf505d6fb6d6ceccf04a9ec50ae
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67524136"
---
# <a name="get-user-related-machines-api"></a>Obtención de la API de máquinas relacionadas con el usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API
Recupera una colección de dispositivos relacionados con un identificador de usuario determinado.

## <a name="limitations"></a>Limitaciones

Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application |Machine.Read.All|"Leer todos los perfiles de máquina"
Application |Machine.ReadWrite.All |"Leer y escribir toda la información de la máquina"
Delegado (cuenta profesional o educativa) | Machine.Read | "Leer información de la máquina"
Delegado (cuenta profesional o educativa) | Machine.ReadWrite | "Leer y escribir información de la máquina"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos". Para obtener más información, consulte [Creación y administración de roles](user-roles.md).
> - La respuesta incluirá solo los dispositivos a los que el usuario pueda acceder, en función de la configuración del grupo de dispositivos. Para obtener más información, consulte [Creación y administración de grupos de dispositivos](machine-groups.md).

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/users/{id}/machines
```

**El identificador no es el UPN completo, sino solo el nombre de usuario. (por ejemplo, para recuperar máquinas para user1@contoso.com use /api/users/user1/machines)**

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si es correcto y el usuario existe: 200 Aceptar con la lista de entidades de [máquina](machine.md) en el cuerpo. Si el usuario no existe: 200 Aceptar con un conjunto vacío.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
