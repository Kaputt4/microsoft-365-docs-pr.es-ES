---
title: Propiedades y métodos de puntuación
description: Recupera la puntuación de exposición de la organización, la puntuación de seguridad del dispositivo y la puntuación de exposición por grupo de dispositivos.
keywords: api, graph api, api admitidas, puntuación, puntuación de exposición, puntuación de seguridad del dispositivo, puntuación de exposición por grupo de dispositivos
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: cbb0951b9fb7576e815ffcfc0a44ca2ad6e44fa1
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67693915"
---
# <a name="score-resource-type"></a>Puntuación del tipo de recurso

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Métodos

Método|Tipo de valor devuelto|Descripción
:---|:---|:---
[Obtener puntuación de exposición](get-exposure-score.md)|[Puntuación](score.md)|Obtenga la puntuación de exposición de la organización.
[Obtener puntuación segura para dispositivos](get-device-secure-score.md)|[Puntuación](score.md)|Obtenga la puntuación de seguridad del dispositivo de la organización.
[Enumeración de la puntuación de exposición por grupo de dispositivos](get-machine-group-exposure-score.md)|[Puntuación](score.md)|Enumera las puntuaciones por grupo de dispositivos.

## <a name="properties"></a>Propiedades

Propiedad|Tipo|Descripción
:---|:---|:---
Puntuación|Doble|Puntuación actual.
Hora|DateTime|Fecha y hora en que se realizó la llamada a esta API.
RbacGroupName|Cadena|Nombre del grupo de dispositivos.
RbacGroupId|Cadena|Identificador del grupo de dispositivos.
