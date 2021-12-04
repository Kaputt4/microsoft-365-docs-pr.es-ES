---
title: Propiedades y métodos de puntuación
description: Recupera la puntuación de exposición de la organización, la puntuación segura del dispositivo y la puntuación de exposición por grupo de dispositivos
keywords: api, api de gráfico, api admitidas, puntuación, puntuación de exposición, puntuación segura del dispositivo, puntuación de exposición por grupo de dispositivos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: fe69b42c2d8bf80089b749cd41e59664cc2921e3
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300987"
---
# <a name="score-resource-type"></a>Tipo de recurso Score

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methods

Método|Tipo de valor devuelto|Description
:---|:---|:---
[Obtener puntuación de exposición](get-exposure-score.md)|[Puntuación](score.md)|Obtener la puntuación de exposición de la organización.
[Obtener puntuación segura para dispositivos](get-device-secure-score.md)|[Puntuación](score.md)|Obtiene la puntuación segura del dispositivo de la organización.
[Puntuación de exposición de lista por grupo de dispositivos](get-machine-group-exposure-score.md)|[Puntuación](score.md)|Enumera las puntuaciones por grupo de dispositivos.

## <a name="properties"></a>Propiedades

Propiedad|Tipo|Description
:---|:---|:---
Puntuación|Doble|La puntuación actual.
Hora|DateTime|La fecha y hora en que se realizó la llamada para esta API.
RbacGroupName|String|El nombre del grupo de dispositivos.
RbacGroupId|String|Id. del grupo de dispositivos.
