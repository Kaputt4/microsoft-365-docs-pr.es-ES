---
title: Propiedades y métodos de la biblioteca de respuestas inmediatas
description: Obtenga información sobre cómo usar los métodos y propiedades de la biblioteca de respuestas en directo.
keywords: api, api de gráfico, api admitidas, get, dispositivos
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
ms.technology: m365d
ms.openlocfilehash: c9eb1de08be8905a41b172a19a33db58dbdc19b9
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525853"
---
#  <a name="live-response-library-methods-and-properties"></a>Propiedades y métodos de la biblioteca de respuestas inmediatas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Métodos

| **Método**          | **Tipo de valor devuelto**         | **Descripción**                         |
|---------------------|-------------------------|-----------------------------------------|
| Archivos de biblioteca de lista  | Colección de archivos de biblioteca | Enumerar entidades de archivo de biblioteca              |
| Upload a la biblioteca   | Entidad de archivo de biblioteca     | Upload un archivo a una biblioteca de respuestas en directo |
| Eliminar de la biblioteca | Sin contenido              | Eliminar entidad de archivo de biblioteca              |

## <a name="properties"></a>Propiedades

| **Propiedad** | **Tipo**                         | **Descripción**                                        |
|--------------|----------------------------------|--------------------------------------------------------|
| Comandos     | Colección de comandos Live Response | Matriz de objetos Command. Consulta [comandos de respuesta en directo](live-response.md#live-response-commands). |

