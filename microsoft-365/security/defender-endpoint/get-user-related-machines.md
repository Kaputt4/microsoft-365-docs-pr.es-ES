---
title: Obtener api de máquinas relacionadas con el usuario
description: Obtenga información sobre cómo usar la API Obtener máquinas relacionadas con el usuario para recuperar una colección de dispositivos relacionados con un identificador de usuario en Microsoft Defender para endpoint.
keywords: api, api de gráfico, api admitidas, obtener, usuario, alertas relacionadas con el usuario
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
ms.openlocfilehash: 135dc1d76a1a90cd7fffba0638211d716865cb0c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166806"
---
# <a name="get-user-related-machines-api"></a>Obtener api de máquinas relacionadas con el usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API
Recupera una colección de dispositivos relacionados con un identificador de usuario determinado.


## <a name="limitations"></a>Limitaciones
1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   Machine.Read.All |  'Leer todos los perfiles de máquina'
Aplicación |   Machine.ReadWrite.All | 'Leer y escribir toda la información de la máquina'
Delegado (cuenta profesional o educativa) | Machine.Read | 'Leer información de máquina'
Delegado (cuenta profesional o educativa) | Machine.ReadWrite | 'Leer y escribir información de máquina'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener al menos el siguiente permiso de función: "Ver datos". Para obtener más información, vea [Create and manage roles](user-roles.md) )
>- La respuesta incluirá solo los dispositivos a los que el usuario pueda tener acceso, en función de la configuración del grupo de dispositivos. Para obtener más información, consulta [Crear y administrar grupos de dispositivos.](machine-groups.md)

## <a name="http-request"></a>Solicitud HTTP
```
GET /api/users/{id}/machines
```

**El identificador no es el UPN completo, sino solo el nombre de usuario. (por ejemplo, para recuperar máquinas para user1@contoso.com usar /api/users/user1/machines)**


## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.


## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente y el usuario existe: 200 Aceptar con la lista de [entidades](machine.md) de máquina en el cuerpo. Si el usuario no existe: 404 No encontrado.


## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
