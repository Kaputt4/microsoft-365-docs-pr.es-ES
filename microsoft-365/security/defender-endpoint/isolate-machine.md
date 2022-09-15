---
title: Aislar la API de máquina
description: Obtenga información sobre cómo usar isolate machine API para aislar un dispositivo de acceso a la red externa en Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, aislar el dispositivo
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
ms.openlocfilehash: 727389e9d6b1d21662e7ca0b8a1753fa242ec56e
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67704686"
---
# <a name="isolate-machine-api"></a>Aislar la API de máquina

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Aísla un dispositivo del acceso a la red externa.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - El aislamiento completo está disponible para dispositivos en Windows 10, versión 1703 y en Windows 11.
> - El aislamiento selectivo está disponible para dispositivos en Windows 10, versión 1709 o posterior y en Windows 11.
> - Al aislar un dispositivo, solo se permiten determinados procesos y destinos. Por lo tanto, los dispositivos que están detrás de un túnel VPN completo no podrán acceder al servicio en la nube Microsoft Defender para punto de conexión después de que el dispositivo esté aislado. Se recomienda usar una VPN de túnel dividido para Microsoft Defender para punto de conexión y el tráfico relacionado con la protección basada en la nube del Antivirus de Microsoft Defender.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Machine.Isolate|"Aislar máquina"
Delegado (cuenta profesional o educativa)|Machine.Isolate|"Aislar máquina"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Acciones de corrección activas" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).
> - El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulte [Creación y administración de grupos de dispositivos](machine-groups.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|string|application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los parámetros siguientes:

Parámetro|Tipo|Descripción
:---|:---|:---
Comentario|Cadena|Comentario que se va a asociar a la acción. **Necesario**.
IsolationType|Cadena|Tipo del aislamiento. Los valores permitidos son: "Full" o "Selective".

**IsolationType** controla el tipo de aislamiento que se va a realizar y puede ser uno de los siguientes:

- Completo: aislamiento completo
- Selectivo: restringir solo el acceso de un conjunto limitado de aplicaciones a la red (consulte [Aislar dispositivos de la red](respond-machine-alerts.md#isolate-devices-from-the-network) para obtener más información)

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 201: código de respuesta creado y [Acción de máquina](machineaction.md) en el cuerpo de la respuesta.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- Para liberar un dispositivo del aislamiento, consulte [Liberación del dispositivo del aislamiento](unisolate-machine.md).
