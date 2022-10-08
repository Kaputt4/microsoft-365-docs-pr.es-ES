---
title: API agregar o quitar etiquetas de máquina
description: Obtenga información sobre cómo usar la API Agregar o quitar etiquetas de máquina para agregar o quitar una etiqueta para una máquina en Microsoft Defender para punto de conexión.
keywords: api, graph api, api admitidas, etiquetas, etiquetas de máquina
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
ms.openlocfilehash: 3f6139d50e0c1f565952e853f80a325af3afb26e
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68150273"
---
# <a name="add-or-remove-machine-tags-api"></a>API de agregar o quitar etiquetas de máquina

**Se aplica a:**

- [plan 1 de Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [plan 2 de Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Agrega o quita la etiqueta a una [máquina](machine.md) específica.

## <a name="limitations"></a>Limitaciones

1. Puede publicar en las máquinas que se vieron por última vez según el período de retención configurado.

2. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Defender para API de punto de conexión](apis-intro.md).

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Machine.ReadWrite.All|"Leer y escribir toda la información de la máquina"
Delegado (cuenta profesional o educativa)|Machine.ReadWrite|"Leer y escribir información de la máquina"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Administrar configuración de seguridad". Para obtener más información (consulte [Creación y administración de roles](user-roles.md) ).
> - El usuario debe tener acceso a la máquina en función de la configuración del grupo de máquinas (consulte [Creación y administración de grupos de máquinas](machine-groups.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
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
Valor|Cadena|Nombre de la etiqueta. **Necesario**.
Acción|Enum|Agregar o quitar. Los valores permitidos son: "Add" o "Remove". **Necesario**.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve el código de respuesta 200 - Ok y la máquina actualizada en el cuerpo de la respuesta.

## <a name="example-request"></a>Solicitud de ejemplo

Este es un ejemplo de una solicitud que agrega la etiqueta de máquina.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

Para quitar la etiqueta de máquina, establezca la acción en "Quitar" en lugar de "Agregar" en el cuerpo de la solicitud.
