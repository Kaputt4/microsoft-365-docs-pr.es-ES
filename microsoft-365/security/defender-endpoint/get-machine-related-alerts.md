---
title: Obtención de la API de alertas relacionadas con la máquina
description: Obtenga información sobre cómo usar la API Obtener alertas relacionadas con la máquina. Esta API le permite recuperar todas las alertas relacionadas con un dispositivo específico en Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, get, devices, related, alerts
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
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: e21768996f7b102701430b296596cd0515e3838d
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68173572"
---
# <a name="get-machine-related-alerts--api"></a>Obtención de la API de alertas relacionadas con la máquina

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera todas las [alertas relacionadas](alerts.md) con un dispositivo específico.

## <a name="limitations"></a>Limitaciones

1. Puede consultar en los dispositivos actualizados por última vez según el período de retención configurado.
2. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Alert.Read.All|"Leer todas las alertas"
Application|Alert.ReadWrite.All|"Leer y escribir todas las alertas"
Delegado (cuenta profesional o educativa) | Alert.Read | "Leer alertas"
Delegado (cuenta profesional o educativa) | Alert.ReadWrite | "Alertas de lectura y escritura"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos". Para obtener más información sobre los permisos, consulte [Creación y administración de roles](user-roles.md).
> - El usuario debe tener acceso al dispositivo, en función de la configuración del grupo de dispositivos. Para obtener más información sobre la configuración del grupo de dispositivos, consulte [Creación y administración de grupos de dispositivos](machine-groups.md).
>
> La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión.
## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | Cadena | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente y el dispositivo existe: 200 Aceptar con la lista de entidades de [alerta](alerts.md) en el cuerpo. Si no se encontró el dispositivo: 404 No encontrado.
