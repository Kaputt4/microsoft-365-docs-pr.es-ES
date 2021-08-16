---
title: Ejecutar LA API de detección antivirus
description: Usa esta API para crear llamadas relacionadas con la ejecución de un examen antivirus en un dispositivo.
keywords: api, api de gráfico, api admitidas, quitar el dispositivo del aislamiento
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
ms.openlocfilehash: 2ae3c72387b2617bc8fe88349272d27675af16a5
ms.sourcegitcommit: 99817013bcb26b7ed051e011c8addb716cc91d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58349217"
---
# <a name="run-antivirus-scan-api"></a>Ejecutar LA API de detección antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Inicie Antivirus de Microsoft Defender examen en un dispositivo.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - Esta acción está disponible para dispositivos Windows 10 versión 1709 o posterior.
> - Un Antivirus de Microsoft Defender (Antivirus de Microsoft Defender) puede ejecutarse junto con otras soluciones antivirus, independientemente de si Antivirus de Microsoft Defender es la solución antivirus activa o no. Microsoft Defender AV puede estar en modo pasivo. Para obtener más información, [vea Antivirus de Microsoft Defender compatibilidad](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility.md).

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Machine.Scan|'Máquina de digitalización'
Delegado (cuenta profesional o educativa)|Machine.Scan|'Máquina de digitalización'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)
> - El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Autorización|String|Portador {token}. **Necesario**.
Content-Type|string|application/json

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro|Tipo|Descripción
:---|:---|:---
Comentario|Cadena|Comentario para asociarlo a la acción. **Necesario**.
ScanType|String|Define el tipo de examen. **Necesario**.

**ScanType** controla el tipo de examen que se va a realizar y puede ser uno de los siguientes:

- **Rápido:** realizar un examen rápido en el dispositivo
- **Full**: Realizar un examen completo en el dispositivo

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 201, Código de respuesta creado y _Objeto MachineAction_ en el cuerpo de la respuesta.

Si envías varias llamadas API para ejecutar un examen antivirus para el mismo dispositivo, devuelve "acción del equipo pendiente" o HTTP 400 con el mensaje "La acción ya está en curso".

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
