---
title: Propiedades y métodos de puntuación
description: Recupera la puntuación de exposición de la organización, la puntuación segura del dispositivo y la puntuación de exposición por grupo de dispositivos
keywords: api, api de gráfico, api admitidas, puntuación, puntuación de exposición, puntuación segura del dispositivo, puntuación de exposición por grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200166"
---
# <a name="score-resource-type"></a>Tipo de recurso Score

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methods

Método |Tipo de valor devuelto |Descripción
:---|:---|:---
[Obtener puntuación de exposición](get-exposure-score.md) | [Puntuación](score.md) | Obtener la puntuación de exposición de la organización.
[Obtener puntuación segura del dispositivo](get-device-secure-score.md) | [Puntuación](score.md) | Obtiene la puntuación segura del dispositivo de la organización.
[Puntuación de exposición de lista por grupo de dispositivos](get-machine-group-exposure-score.md)| [Puntuación](score.md) | Enumera las puntuaciones por grupo de dispositivos.

## <a name="properties"></a>Propiedades

Propiedad |  Tipo    |   Descripción
:---|:---|:---
Puntuación | Doble | La puntuación actual.
Hora | DateTime | La fecha y hora en que se realizó la llamada para esta API.
RbacGroupName | Cadena | El nombre del grupo de dispositivos.
