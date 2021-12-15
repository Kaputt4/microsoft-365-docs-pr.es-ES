---
title: Solucionar problemas de licencia para Microsoft Defender para Endpoint en Mac
description: Solucionar problemas de licencia en Microsoft Defender para Endpoint en Mac.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, performance
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b7a12d2eb88998496c4998396a5d7bf5084656e8
ms.sourcegitcommit: b6ab10ba95e4b986065c51179ead3810cc1e2a85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "61520973"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solucionar problemas de licencia para Microsoft Defender para Endpoint en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para endpoint en macOS](microsoft-defender-endpoint-mac.md) 
 [Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037) 
 de Microsoft Defender para endpoint [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Mientras estás pasando por Microsoft Defender para endpoint en [macOS](microsoft-defender-endpoint-mac.md) [y](mac-install-manually.md) pruebas de implementación manual o una prueba de concepto (PoC), es posible que recibas el siguiente error:

![Imagen de error de licencia.](images/no-license-found.png)

**Mensaje:** 

No se encontró ninguna licencia

Parece que su organización no tiene una licencia para Microsoft 365 Enterprise suscripción.

Póngase en contacto con el administrador para obtener ayuda.

**Causa:** 

Implementó o instaló el paquete de Microsoft Defender para endpoint en macOS ("Descargar paquete de instalación"), pero es posible que no haya ejecutado el script de configuración ("Descargar paquete de incorporación") o que no haya asignado una licencia al usuario.

También puede encontrar este error cuando el agente de Microsoft Defender para endpoint en macOS no está actualizado. 


**Solución:**

Siga las instrucciones MicrosoftDefenderATPOnboardingMacOs.py documentadas aquí: [Configuración de cliente](mac-install-manually.md#client-configuration)

Para escenarios en los que Microsoft Defender para Endpoint en macOS no está actualizado, tendrás que actualizar el agente. 
