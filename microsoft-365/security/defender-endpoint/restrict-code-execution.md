---
title: Restricción de la API de ejecución de aplicaciones
description: Use esta API para crear llamadas relacionadas con la restricción de la ejecución de una aplicación.
keywords: apis, graph api, api admitidas, recopilar paquete de investigación
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 765f08fe38d8b04d76c191c9e31c7a33c9b56ff7
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331603"
---
# <a name="restrict-app-execution-api"></a>Restricción de la API de ejecución de aplicaciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Restrinja la ejecución de todas las aplicaciones del dispositivo excepto un conjunto predefinido.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

[!include[Device actions note](../../includes/machineactionsnote.md)]


> [!IMPORTANT]
>
> - Esta acción está disponible para dispositivos en Windows 10, versión 1709 o posterior, y en Windows 11.
> - Esta característica está disponible si su organización usa el Antivirus de Microsoft Defender.
> - Esta acción debe cumplir los requisitos de firma y formatos de directiva de integridad de código Windows Defender Control de aplicaciones. Para obtener más información, consulte [Formatos y firma de directivas de integridad de código](/windows/device-security/device-guard/requirements-and-deployment-planning-guidelines-for-device-guard#code-integrity-policy-formats-and-signing).

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Uso de api de Microsoft Defender para punto de conexión](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Machine.RestrictExecution|"Restringir la ejecución de código"
Delegado (cuenta profesional o educativa)|Machine.RestrictExecution|"Restringir la ejecución de código"

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de rol: "Acciones de corrección activas" (consulte [Creación y administración de roles](user-roles.md) para obtener más información).
> - El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulte [Creación y administración de grupos de dispositivos](machine-groups.md) para obtener más información).

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
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

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 201: código de respuesta creado y [Acción de máquina](machineaction.md) en el cuerpo de la respuesta.

Si envía varias llamadas API para restringir la ejecución de la aplicación para el mismo dispositivo, devuelve "acción de máquina pendiente" o HTTP 400 con el mensaje "La acción ya está en curso".

## <a name="example"></a>Ejemplo

### <a name="request"></a>Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}
```

- Para quitar la restricción de ejecución de código de un dispositivo, consulte [Quitar restricción de aplicación](unrestrict-code-execution.md).
