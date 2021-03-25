---
title: Solucionar problemas de licencia para ATP de Microsoft Defender para Mac
description: Solucionar problemas de licencia en ATP de Microsoft Defender para Mac.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074467"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Solucionar problemas de licencia para Microsoft Defender para Endpoint para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para endpoint para Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Mientras estás pasando por Microsoft Defender [](mac-install-manually.md) para endpoint [para Mac](microsoft-defender-endpoint-mac.md) y pruebas de implementación manual o una prueba de concepto (PoC), es posible que recibas el siguiente error:

![Imagen de error de licencia](images/no-license-found.png)

**Mensaje:** 

No se encontró ninguna licencia

Parece que su organización no tiene una licencia para la suscripción a Microsoft 365 Enterprise.

Póngase en contacto con el administrador para obtener ayuda.

**Causa:** 

Implementó o instaló el paquete de Microsoft Defender para endpoint para macOS ("Descargar paquete de instalación") pero es posible que haya ejecutado el script de configuración ("Descargar paquete de incorporación").

**Solución:**

Siga las instrucciones MicrosoftDefenderATPOnboardingMacOs.py documentadas aquí: [Configuración de cliente](mac-install-manually.md#client-configuration)

