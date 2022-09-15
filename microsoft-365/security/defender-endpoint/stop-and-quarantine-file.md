---
title: API de archivo de detención y cuarentena
description: Obtenga información sobre cómo detener la ejecución de un archivo en un dispositivo y eliminar el archivo en Microsoft Defender para punto de conexión. Consulte un ejemplo.
keywords: apis, graph api, api admitidas, archivo de detención y cuarentena
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
ms.openlocfilehash: 4e301b2b73b2a30b40ca281e2e383cadedbe19ff
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67704026"
---
# <a name="stop-and-quarantine-file-api"></a>API de archivo de detención y cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Detenga la ejecución de un archivo en un dispositivo y elimínelo.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
> Solo puede realizar esta acción si:
>
> - El dispositivo en el que va a realizar la acción ejecuta Windows 10, versión 1703 o posterior, o Windows 11
> - El archivo no pertenece a editores de terceros de confianza o no está firmado por Microsoft
> - Antivirus de Microsoft Defender debe ejecutarse al menos en modo pasivo. Para obtener más información, consulte [Compatibilidad del Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).


## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Machine.StopAndQuarantine|"Detener y poner en cuarentena"
Application|Machine.Read.All|"Leer todos los perfiles de máquina"
Application|Machine.ReadWrite.All|"Leer y escribir toda la información de la máquina"
Delegado (cuenta profesional o educativa)|Machine.StopAndQuarantine|"Detener y poner en cuarentena"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Acciones de corrección activas" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).
> - El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulte [Creación y administración de grupos de dispositivos](machine-groups.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
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
Sha1|Cadena|Sha1 del archivo que se va a detener y poner en cuarentena en el dispositivo. **Necesario**.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 201: código de respuesta creado y [Acción de máquina](machineaction.md) en el cuerpo de la respuesta.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}
```
