---
title: API de máquina fuera del panel
description: Obtenga información sobre cómo usar una API para desconectar un dispositivo de Microsoft Defender para punto de conexión.
keywords: apis, graph api, api admitidas, recopilar paquete de investigación
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
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 03b7c2b9af508740475ef6859788fec7ed91b866
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68770066"
---
# <a name="offboard-machine-api"></a>API de máquina fuera del panel

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Dispositivo fuera del panel de Defender para punto de conexión.

## <a name="limitations"></a>Limitaciones

- Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

  [!include[Machine actions note](../../includes/machineactionsnote.md)]

> [!NOTE]
> Esta API se admite en Windows 11, Windows 10, versión 1703 y versiones posteriores; en Windows Server 2019 y versiones posteriores; y en Windows Server 2012 R2 y Windows Server 2016 al usar el [nuevo agente unificado para Defender para punto de conexión](update-agent-mma-windows.md#upgrade-to-the-new-unified-agent-for-defender-for-endpoint).
> Esta API no se admite en dispositivos macOS o Linux.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de Defender para API de punto de conexión](apis-intro.md).

Tipo de permiso|Permiso|Nombre para mostrar del permiso
---|---|---
Application|Machine.Offboard|'Offboard machine'
Delegado (cuenta profesional o educativa)|Machine.Offboard|'Offboard machine'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario necesita el rol de AD "Administración global"
> - El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulte [Creación y administración de grupos de dispositivos](machine-groups.md) para obtener más información).
>
> La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión.  

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

El identificador de equipo se puede encontrar en la dirección URL al seleccionar el dispositivo. Por lo general, es un número alfanumérico de 40 dígitos que se puede encontrar en la dirección URL.

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
---|---|---
Authorization|Cadena|Portador {token}. **Necesario**.
Content-Type|string|application/json. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los parámetros siguientes:

Parámetro|Tipo|Descripción
---|---|---
Comentario|Cadena|Comentario que se va a asociar a la acción. **Necesario**.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200: código de respuesta creado y [Acción de máquina](machineaction.md) en el cuerpo de la respuesta.

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud. Si no se agrega ningún comentario JSON, se producirá un error con el código **400**.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
