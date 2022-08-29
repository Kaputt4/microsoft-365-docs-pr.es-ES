---
title: Obtener puntuación segura para dispositivos
description: Recupera la puntuación de seguridad del dispositivo de la organización.
keywords: apis, graph api, api admitidas, get, alerts, recent
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 07651ed756d8229e6f0f4712b230875c11bf8007
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327693"
---
# <a name="get-device-secure-score"></a>Obtener puntuación segura para dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Recupera la [puntuación de seguridad de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md). Una puntuación de seguridad de Microsoft más alta para dispositivos significa que los puntos de conexión son más resistentes frente a ataques de amenazas de ciberseguridad.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API](apis-intro.md) para obtener más información.

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Score.Read.All|"Leer la puntuación de administración de amenazas y vulnerabilidades"
Delegado (cuenta profesional o educativa)|Score.Read|"Leer la puntuación de administración de amenazas y vulnerabilidades"

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/configurationScore
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK, con los datos de puntuación segura del dispositivo en el cuerpo de la respuesta.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

> [!NOTE]
> La lista de respuestas que se muestra aquí puede truncarse por brevedad.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a>Vea también

- [Consultas de OData con Microsoft Defender para punto de conexión](exposed-apis-odata-samples.md)
