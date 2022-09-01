---
title: Propiedades y métodos de la biblioteca de respuestas inmediatas
description: Obtenga información sobre cómo usar los métodos y las propiedades de la biblioteca de respuestas dinámicas.
keywords: apis, graph api, api admitidas, get, devices
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
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
ms.subservice: m365d
ms.openlocfilehash: 8338805bebc21e538242ebb902a5d581d5af42f5
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520827"
---
#  <a name="live-response-library-methods-and-properties"></a>Propiedades y métodos de la biblioteca de respuestas inmediatas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Métodos

| **Método**          | **Tipo de valor devuelto**         | **Descripción**                         |
|---------------------|-------------------------|-----------------------------------------|
| Archivos de biblioteca de lista  | Colección de archivos de biblioteca | Enumeración de entidades de archivo de biblioteca              |
| Carga en la biblioteca   | Entidad de archivo de biblioteca     | Carga de un archivo en la biblioteca de respuesta activa |
| Eliminar de la biblioteca | Sin contenido              | Eliminar entidad de archivo de biblioteca              |

## <a name="properties"></a>Propiedades

| **Propiedad** | **Tipo**                         | **Descripción**                                        |
|--------------|----------------------------------|--------------------------------------------------------|
| Comandos     | Colección de comandos live response | Matriz de objetos Command. Consulte [comandos de respuesta dinámica](live-response.md#live-response-commands). |

