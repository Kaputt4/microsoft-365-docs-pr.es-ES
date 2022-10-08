---
title: Tipo de recurso de usuario
description: Recupere las alertas de Microsoft Defender para punto de conexión recientes relacionadas con los usuarios.
keywords: apis, graph api, api admitidas, get, alerts, recent
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: af00cc62ae86b31c440353a8885941856b94d6d7
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68225556"
---
# <a name="user-resource-type"></a>Tipo de recurso de usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Método|Tipo de valor devuelto|Descripción
---|---|---
[Enumerar alertas relacionadas con el usuario](get-user-related-alerts.md)|Colección [alert](alerts.md)|Enumere todas las alertas asociadas a un [usuario](user.md).
[Enumerar dispositivos relacionados con el usuario](get-user-related-machines.md)|[colección de máquinas](machine.md)|Enumere todos los dispositivos que ha iniciado sesión un [usuario](user.md).
