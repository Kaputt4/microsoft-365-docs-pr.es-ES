---
title: Solución de problemas de licencia para Microsoft Defender para punto de conexión en Mac
description: Solución de problemas de licencia en Microsoft Defender para punto de conexión en Mac.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, performance
ms.service: microsoft-365-security
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
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 4188208bd6efed26c2c612629f57274d8328934c
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67692374"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solución de problemas de licencia para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md)
 [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
 [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Mientras pasa por [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md) y pruebas [de implementación manual](mac-install-manually.md) o una prueba de concepto (PoC), es posible que obtenga el siguiente error:

:::image type="content" source="images/no-license-found.png" alt-text="Error de licencia" lightbox="images/no-license-found.png":::

**Mensaje:** 

No se encontró ninguna licencia

Parece que su organización no tiene una licencia para Microsoft 365 Enterprise suscripción.

Póngase en contacto con el administrador para obtener ayuda.

**Causa:** 

Ha implementado o instalado el Microsoft Defender para punto de conexión en el paquete macOS ("Descargar paquete de instalación"), pero es posible que no haya ejecutado el script de configuración ("Descargar paquete de incorporación") o que no haya asignado una licencia al usuario.

También puede encontrar este error cuando el Microsoft Defender para punto de conexión en el agente de macOS no está actualizado. 


**Solución:**

Siga las instrucciones de MicrosoftDefenderATPOnboardingMacOs.py que se documentan aquí: [Configuración del cliente](mac-install-manually.md#client-configuration)

En escenarios en los que Microsoft Defender para punto de conexión en macOS no está actualizado, deberá actualizar el agente. 
