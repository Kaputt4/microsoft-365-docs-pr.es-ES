---
title: Obtener información de alerta por API de id.
description: Obtenga información sobre cómo usar la API Obtener información de alerta por ID para recuperar una alerta específica por su identificador en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, alert, information, id
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
ms.openlocfilehash: a9a4505ec4609dc42ec75159c2d905d16e01b559
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53656840"
---
# <a name="get-alert-information-by-id-api"></a>Obtener información de alerta por API de id.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera alerta [específica por](alerts.md) su identificador.

## <a name="limitations"></a>Limitaciones

1. Puede obtener las alertas por última vez actualizadas según el período de retención configurado.
2. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Alert.Read.All|'Leer todas las alertas'
Aplicación|Alert.ReadWrite.All|'Leer y escribir todas las alertas'
Delegado (cuenta profesional o educativa)|Alert.Read|'Leer alertas'
Delegado (cuenta profesional o educativa)|Alert.ReadWrite|'Leer y escribir alertas'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
> - El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/alerts/{id}
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200 Ok y la entidad [alert](alerts.md) en el cuerpo de la respuesta. Si no se encontró la alerta con el identificador especificado: 404 No encontrado.
