---
title: Obtención de la API de alertas relacionadas con el dominio
description: Obtenga información sobre cómo usar la API Obtener alertas relacionadas con el dominio para recuperar alertas relacionadas con una dirección de dominio determinada en Microsoft Defender para punto de conexión.
keywords: api, graph api, api admitidas, get, domain, related, alerts
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
search.appverid: met150
ms.openlocfilehash: 1b3e9e69bc24413624a922f7b88fe4550869f195
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698769"
---
# <a name="get-domain-related-alerts-api"></a>Obtención de la API de alertas relacionadas con el dominio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera una colección de [alertas](alerts.md) relacionadas con una dirección de dominio determinada.

## <a name="limitations"></a>Limitaciones

- Puede consultar las alertas actualizadas por última vez según el período de retención configurado.
- Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Alert.Read.All|"Leer todas las alertas"
Application|Alert.ReadWrite.All|"Leer y escribir todas las alertas"
Delegado (cuenta profesional o educativa)|Alert.Read|"Leer alertas"
Delegado (cuenta profesional o educativa)|Alert.ReadWrite|"Alertas de lectura y escritura"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Ver datos" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).
> - La respuesta incluirá solo alertas asociadas a dispositivos a las que el usuario tenga acceso, según la configuración del grupo de dispositivos (consulte [Creación y administración de grupos de dispositivos](machine-groups.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a>Encabezados de solicitud

|Encabezado|Valor|
|---|---|
|Authorization|Cadena|

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si es correcto y el dominio existe: 200 Aceptar con la lista de entidades de [alerta](alerts.md) . Si el dominio no existe: 200 Aceptar con un conjunto vacío.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Este es un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
