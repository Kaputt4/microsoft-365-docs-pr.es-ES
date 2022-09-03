---
title: Ejecución de la API de examen antivirus
description: Use esta API para crear llamadas relacionadas con la ejecución de un examen antivirus en un dispositivo.
keywords: apis, graph api, api admitidas, quitar el dispositivo del aislamiento
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
ms.openlocfilehash: 0d952848afed65f622e23d490a1b34fdfc593b0b
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67579168"
---
# <a name="run-antivirus-scan-api"></a>Ejecución de la API de examen antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Inicie el examen del Antivirus de Microsoft Defender en un dispositivo.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - Esta acción está disponible para dispositivos en Windows 10, versión 1709 o posterior, y en Windows 11.
> - Un examen del Antivirus de Microsoft Defender se puede ejecutar junto con otras soluciones antivirus, independientemente de si antivirus de Microsoft Defender es la solución antivirus activa o no. Antivirus de Microsoft Defender puede estar en modo pasivo. Para obtener más información, consulte [Compatibilidad del Antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-compatibility).

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Machine.Scan|"Máquina de examen"
Delegado (cuenta profesional o educativa)|Machine.Scan|"Máquina de examen"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Acciones de corrección activas" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).
> - El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulte [Creación y administración de grupos de dispositivos](machine-groups.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|string|application/json

## <a name="request-body"></a>Cuerpo de solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los parámetros siguientes:

Parámetro|Tipo|Descripción
:---|:---|:---
Comentario|Cadena|Comentario que se va a asociar a la acción. **Necesario**.
ScanType|Cadena|Define el tipo de examen. **Necesario**.

**ScanType** controla el tipo de examen que se va a realizar y puede ser uno de los siguientes:

- **Rápido**: Realizar un examen rápido en el dispositivo
- **Completo**: realizar un examen completo en el dispositivo

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 201, Código de respuesta creado y objeto _MachineAction_ en el cuerpo de la respuesta.

Si envía varias llamadas API para ejecutar un examen antivirus para el mismo dispositivo, devuelve "acción de máquina pendiente" o HTTP 400 con el mensaje "La acción ya está en curso".

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```
