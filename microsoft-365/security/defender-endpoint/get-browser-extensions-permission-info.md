---
title: Obtener información de permisos de extensiones de explorador
description: Recupera una lista de todos los permisos necesarios para una extensión del explorador.
keywords: api, graph api, api admitidas, get, información de extensión del explorador, Microsoft Defender para punto de conexión, Administración de vulnerabilidades de Microsoft Defender
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
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
ms.openlocfilehash: c67b731e313e6ac703b6990193bad245b10f20c6
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68190779"
---
# <a name="get-browser-extensions-permission-information"></a>Obtener información de permisos de extensiones de explorador

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una evaluación gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> ¿Quieres experimentar Administración de vulnerabilidades de Microsoft Defender? Obtenga más información sobre cómo puede registrarse en la [versión de prueba de Administración de vulnerabilidades de Microsoft Defender versión preliminar pública](../defender-vulnerability-management/get-defender-vulnerability-management.md).

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>Descripción de la API

Recupera una lista de todos los permisos solicitados por una extensión de explorador específica. Se trata de una descripción de datos estática y se usaría principalmente para mejorar los datos [devueltos por la API de evaluación de extensiones del explorador Export](get-assessment-browser-extensions.md).

Mediante la combinación de estas API, podrá ver una descripción de los permisos solicitados por las extensiones del explorador que se muestran en los resultados de [la evaluación Exportar extensiones de explorador](get-assessment-browser-extensions.md) .

<br>Admite [consultas de OData V4](https://www.odata.org/documentation/).
<br>Operadores compatibles con OData:
<br>```$filter``` on:  ```id```propiedades , ```name```, ```description```, ```cvssV3```, ```publishedOn```, ```severity```y ```updatedOn``` .
<br>```$top``` con un valor máximo de 10 000.
<br>```$skip```.
<br>Vea ejemplos en [consultas de OData con Microsoft Defender para punto de conexión](exposed-apis-odata-samples.md).

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API](apis-intro.md) para obtener más información.

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Software.Read.All|"Leer la información del software de administración de amenazas y vulnerabilidades"
Delegado (cuenta profesional o educativa)|Software.Read|"Leer la información del software de administración de amenazas y vulnerabilidades"

## <a name="http-request"></a>Solicitud HTTP

```http
GET api/browserextensions/permissionsinfo
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
:---|:---|:---
Authorization|Cadena|Portador {token}. **Necesario**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 Ok con la lista de todos los permisos solicitados por una extensión del explorador en el cuerpo.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/browserextensions/permissionsinfo
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#BrowserExtension",
    "value": [
{
  "value": [
    {
      "key": "audioCapture",
      "permissionName": "Capture audio from attached mic or webcam",
      "description": "Capture audio from attached mic or webcam. Could be used to listen in on use."
    },
    {
      "key": "app.window.fullscreen.overrideEsc",
      "permissionName": "Prevent escape button from exiting fullscreen",
      "description": "Can prevent escape button from exiting fullscreen."
    },
    {
      "key": "browsingData",
      "permissionName": "Clear browsing data",
      "description": "Clears browsing data which could result in a forensics/logging issues."
    },
    {
      "key": "content_security_policy",
      "permissionName": "Can manipulate default Content Security Policy (CSP)",
      "description": "CSP works as a block/allow listing mechanism for resources loaded or executed by your extensions. Can manipulate default CSP."
    }

            ]
}
    ]
```

## <a name="see-also"></a>Consulte también

- [Obtener información de permisos de extensiones de explorador](get-assessment-browser-extensions.md)
- [Evaluación de extensiones del explorador](../defender-vulnerability-management/tvm-browser-extensions.md)

## <a name="other-related"></a>Otros relacionados

- [Administración de amenazas y vulnerabilidades](../defender-vulnerability-management/defender-vulnerability-management.md)
- [Vulnerabilidades en la organización](../defender-vulnerability-management/tvm-weaknesses.md)