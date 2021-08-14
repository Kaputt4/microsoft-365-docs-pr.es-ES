---
title: Obtener api de alertas relacionadas con la máquina
description: Obtenga información sobre cómo usar la API Obtener alertas relacionadas con la máquina. Esta API te permite recuperar todas las alertas relacionadas con un dispositivo específico en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, dispositivos, relacionados, alertas
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: cddd84dc362d2193cb63dc18783f280730ba4a6f37df5dc8677bb56899767370
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53811223"
---
# <a name="get-machine-related-alerts--api"></a>Obtener api de alertas relacionadas con la máquina

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera todas las [alertas](alerts.md) relacionadas con un dispositivo específico.

## <a name="limitations"></a>Limitaciones

1. Puede consultar en dispositivos actualizados por última vez de acuerdo con el período de retención configurado.
2. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Alert.Read.All|'Leer todas las alertas'
Aplicación|Alert.ReadWrite.All|'Leer y escribir todas las alertas'
Delegado (cuenta profesional o educativa) | Alert.Read | 'Leer alertas'
Delegado (cuenta profesional o educativa) | Alert.ReadWrite | 'Leer y escribir alertas'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Ver datos". Para obtener más información acerca de los permisos, vea [Create and manage roles](user-roles.md).
> - El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos. Para obtener más información acerca de la configuración del grupo de dispositivos, consulta [Crear y administrar grupos de dispositivos.](machine-groups.md)

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization | String | Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente y el dispositivo existe: 200 Aceptar con la lista [de](alerts.md) entidades de alerta en el cuerpo. Si no se encontró el dispositivo: 404 No encontrado.
