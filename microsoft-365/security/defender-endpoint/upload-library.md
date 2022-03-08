---
title: Cargar archivos en la biblioteca de respuestas en directo
description: Obtenga información sobre cómo cargar un archivo en la biblioteca de respuestas en directo.
keywords: apis, api de gráficos, api admitidas, carga en biblioteca
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b2c50999b7aab3588239f3965e41543680c9aad6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331242"
---
#  <a name="upload-files-to-the-live-response-library"></a>Cargar archivos en la biblioteca de respuestas en directo  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Cargue el archivo en la biblioteca de respuestas en directo.

## <a name="limitations"></a>Limitaciones

1.  La limitación de tamaño máximo de archivo es de 20 MB.

2.  Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Introducción](apis-intro.md).


| Tipo de permiso                    | Permiso     | Nombre para mostrar de permisos        |
|------------------------------------|----------------|--------------------------------|
| Aplicación                        | Library.Manage | Administrar biblioteca de respuestas en directo |
| Delegado (cuenta profesional o educativa) | Library.Manage | Administrar biblioteca de respuestas en directo |

## <a name="http-request"></a>Solicitud HTTP

Cargar

```HTTP
POST https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="request-headers"></a>Encabezados de solicitud

|  Nombre   |    Tipo    |       Descripción                         |
|-----------------|--------|--------------------------------|
| Authorization   | String | Portador.\<token> Obligatorio.      |
| Content-Type    | string | multipart/form-data. Obligatorio. |

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto form-data con los siguientes parámetros:

| Parámetro         |     Tipo         |       Descripción                                        |
|-----------------------|--------------|------------------------------------------------------------|
| Archivo                  | Contenido del archivo | El archivo que se cargará en la biblioteca de respuestas en directo. Obligatorio |
| Descripción           | Cadena       | Descripción del archivo.                                  |
| ParametersDescription | String       | (Opcional) Parámetros necesarios para que se ejecute el script. El valor predeterminado es una cadena vacía.                |
| OverrideIfExists      | Boolean      | (Opcional) Si se va a invalidar el archivo si ya existe. El valor predeterminado es una cadena vacía.          |



## <a name="response"></a>Respuesta

-   Si se realiza correctamente, este método devuelve 200: código de respuesta aceptar y la entidad de biblioteca de respuesta en directo cargada en el cuerpo de la respuesta.

-   Si no se realiza correctamente: este método devuelve 400 - Bad Request.  
    La solicitud incorrecta suele indicar un cuerpo incorrecto.

## <a name="example"></a>Ejemplo

Solicitud

Este es un ejemplo de la solicitud con el bucle.

```CURL
curl -X POST https://api.securitycenter.microsoft.com/api/libraryfiles -H
"Authorization: Bearer \$token" -F "file=\@mdatp1.png" -F
"ParametersDescription=test"  
-F "HasParameters=true" -F "OverrideIfExists=true" -F "Description=test
description"
```

## <a name="related-topic"></a>Tema relacionado

-  [Ejecutar respuesta directa](run-live-response.md) 