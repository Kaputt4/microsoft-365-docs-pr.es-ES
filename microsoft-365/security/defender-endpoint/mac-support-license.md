---
title: Solucionar problemas de licencia para Microsoft Defender para Endpoint en Mac
description: Solucionar problemas de licencia en Microsoft Defender para Endpoint en Mac.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 142ce23d87c1f793a0192270e6d041b33d9bc126
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573972"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solucionar problemas de licencia para Microsoft Defender para Endpoint en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Mientras estás pasando por Microsoft Defender para endpoint en [macOS](microsoft-defender-endpoint-mac.md) [y](mac-install-manually.md) pruebas de implementación manual o una prueba de concepto (PoC), es posible que recibas el siguiente error:

![Imagen de error de licencia.](images/no-license-found.png)

**Mensaje:** 

No se encontró ninguna licencia

Parece que su organización no tiene una licencia para Microsoft 365 Enterprise suscripción.

Póngase en contacto con el administrador para obtener ayuda.

**Causa:** 

Implementó o instaló el paquete de Microsoft Defender para endpoint para macOS ("Descargar paquete de instalación"), pero es posible que haya ejecutado el script de configuración ("Descargar paquete de incorporación") o que no haya asignado una licencia al usuario.

**Solución:**

Siga las instrucciones MicrosoftDefenderATPOnboardingMacOs.py documentadas aquí: [Configuración de cliente](mac-install-manually.md#client-configuration)
