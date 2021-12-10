---
title: Liberar dispositivo de la API de aislamiento
description: Usa esta API para crear llamadas relacionadas para liberar un dispositivo del aislamiento.
keywords: api, api de gráfico, api admitidas, quitar el dispositivo del aislamiento
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e39306a82aa94116d8f7eab8321704c1ffd30efc
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61164219"
---
# <a name="release-device-from-isolation-api"></a>Liberar dispositivo de la API de aislamiento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Deshacer el aislamiento de un dispositivo.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - El aislamiento total está disponible para dispositivos Windows 10, versión 1703.
> - El aislamiento selectivo está disponible para dispositivos Windows 10 versión 1709 o posterior.
> - Al aislar un dispositivo, solo se permiten determinados procesos y destinos. Por lo tanto, los dispositivos que están detrás de un túnel VPN completo no podrán llegar al servicio en la nube de Microsoft Defender para Endpoint después de aislar el dispositivo. Se recomienda usar una VPN de túnel dividido para Microsoft Defender para endpoint y Antivirus de Microsoft Defender tráfico relacionado con la protección basada en la nube.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Machine.Isolate|'Aislar máquina'
Delegado (cuenta profesional o educativa)|Machine.Isolate|'Aislar máquina'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
> - El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|string|application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro|Tipo|Description
:---|:---|:---
Comentario|Cadena|Comentario para asociarlo a la acción. **Necesario**.

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.

Si envías varias llamadas API para quitar el aislamiento del mismo dispositivo, devuelve "acción de máquina pendiente" o HTTP 400 con el mensaje "La acción ya está en curso".

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}
```

Para aislar un dispositivo, consulta [Aislar dispositivo](isolate-machine.md).
