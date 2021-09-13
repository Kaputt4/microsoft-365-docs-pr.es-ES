---
title: Tipo de recurso de usuario
description: Recupera alertas recientes de Microsoft Defender para puntos de conexión relacionadas con los usuarios.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
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
ms.openlocfilehash: 5a3ea32227f64fbf00563f2b48f99b0a21e5510e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214727"
---
# <a name="user-resource-type"></a>Tipo de recurso de usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Método|Tipo de valor devuelto |Descripción
:---|:---|:---
[Enumerar alertas relacionadas con el usuario](get-user-related-alerts.md) | Colección [alert](alerts.md) |  Enumerar todas las alertas asociadas a un [usuario](user.md).
[Enumerar dispositivos relacionados con el usuario](get-user-related-machines.md) | [colección machine](machine.md) | Enumerar todos los dispositivos que un usuario ha iniciado [sesión.](user.md)
