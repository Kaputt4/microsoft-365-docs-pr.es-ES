---
title: OBTENER API de objetos de investigación
description: Usar esta API para crear llamadas relacionadas con obtener el objeto Investigation
keywords: apis, api de gráfico, api admitidas, objeto Investigation
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
ms.openlocfilehash: b54159cfd7e7a8f6d970db1bc7fcb64539061dbd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221349"
---
# <a name="get-investigation-api"></a>Obtener API de investigación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Recupera investigación [específica por](investigation.md) su identificador.
<br> Id. puede ser el identificador de investigación o el identificador de alerta desencadenante de la investigación.


## <a name="limitations"></a>Limitaciones
1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Alert.Read.All|'Leer todas las alertas'
Aplicación|Alert.ReadWrite.All|'Leer y escribir todas las alertas'
Delegado (cuenta profesional o educativa) | Alert.Read | 'Leer alertas'
Delegado (cuenta profesional o educativa) | Alert.ReadWrite | 'Leer y escribir alertas'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200, código de respuesta Ok con una [entidad Investigations.](investigation.md)

