---
title: Obtener api de alertas relacionadas con el dominio
description: Obtenga información sobre cómo usar la API Obtener alertas relacionadas con el dominio para recuperar alertas relacionadas con una dirección de dominio determinada en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, domain, related, alerts
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
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772262"
---
# <a name="get-domain-related-alerts-api"></a>Obtener api de alertas relacionadas con el dominio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descripción de la API
Recupera una colección de [alertas relacionadas](alerts.md) con una dirección de dominio determinada.


## <a name="limitations"></a>Limitaciones
1. Puede consultar las alertas actualizadas por última vez de acuerdo con el período de retención configurado.
2. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.


## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   Alert.Read.All |    'Leer todas las alertas'
Aplicación |   Alert.ReadWrite.All |   'Leer y escribir todas las alertas'
Delegado (cuenta profesional o educativa) | Alert.Read | 'Leer alertas'
Delegado (cuenta profesional o educativa) | Alert.ReadWrite | 'Leer y escribir alertas'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
>- La respuesta incluirá solo alertas, asociadas con dispositivos, a las que el usuario tiene acceso, según la configuración del grupo de dispositivos (vea [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)

## <a name="http-request"></a>Solicitud HTTP
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a>Encabezados de solicitud

| Encabezado        | Valor  |
|:--------------|:-------|
| Authorization | Cadena |

## <a name="request-body"></a>Cuerpo de la solicitud
En blanco

## <a name="response"></a>Respuesta
Si se realiza correctamente y el dominio existe: 200 Aceptar con la lista [de](alerts.md) entidades de alerta. Si el dominio no existe: 404 No encontrado.


## <a name="example"></a>Ejemplo:

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
