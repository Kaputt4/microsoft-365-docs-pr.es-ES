---
title: Tipo de recurso File
description: Recupera alertas recientes de Microsoft Defender para puntos de conexión relacionadas con archivos.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: aa1eaf1cf26af415d134c6a8f0faed5643e787b5
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167807"
---
# <a name="file-resource-type"></a>Tipo de recurso File

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** 
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Representa una entidad de archivo en Defender para endpoint.

## <a name="methods"></a>Methods

Método|Tipo de valor devuelto |Description
:---|:---|:---
[Obtener archivo](get-file-information.md) | [file](files.md) | Obtener un solo archivo 
[Enumerar alertas relacionadas con archivos](get-file-related-alerts.md) | Colección [alert](alerts.md) | Obtener las [entidades](alerts.md) de alerta asociadas al archivo.
[Enumerar máquinas relacionadas con archivos](get-file-related-machines.md) | [colección machine](machine.md) | Obtener las [entidades](machine.md) del equipo asociadas con la alerta.
[estadísticas de archivos](get-file-statistics.md) | Resumen de estadísticas | Recupera la prevalencia del archivo determinado.


## <a name="properties"></a>Propiedades

|Propiedad | Tipo | Description |
|:---|:---|:---|
|sha1 | Cadena | Hash Sha1 del contenido del archivo |
|sha256 | Cadena | Hash Sha256 del contenido del archivo |
|globalPrevalence | Long que admite valores NULL | Prevalencia de archivos en toda la organización |
|globalFirstObserved | DateTimeOffset | Primera vez que se observó el archivo |
|globalLastObserved | DateTimeOffset | Última vez que se observó el archivo |
|size | Long que admite valores NULL | Tamaño del archivo |
|fileType | Cadena | Tipo del archivo |
|isPeFile | Boolean | true si el archivo es ejecutable portátil (por ejemplo, "DLL", "EXE", etc.) |
|filePublisher | Cadena | Editor de archivos |
|fileProductName | Cadena | Nombre del producto |
|firmante | Cadena | Firmante de archivos |
|emisor | Cadena | Emisor de archivos |
|signerHash | Cadena | Hash del certificado de firma |
|isValidCertificate | Boolean | Se ha comprobado correctamente la firma del certificado por Microsoft Defender para el agente de extremo |
|determinationType | Cadena | El tipo de determinación del archivo |
|determinationValue | Cadena | Valor de determinación |

## <a name="json-representation"></a>Representación json

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
