---
title: Solucionar problemas de rendimiento de ATP de Microsoft Defender para Mac
description: Solucionar problemas de rendimiento en ATP de Microsoft Defender para Mac.
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
ms.openlocfilehash: f6dd5681dfafd069a4c52f72e1dc1733584283a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185914"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Solucionar problemas de rendimiento de Microsoft Defender para Endpoint para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para endpoint para Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se proporcionan algunos pasos generales que se pueden usar para limitar los problemas de rendimiento relacionados con Microsoft Defender para Endpoint para Mac.

La protección en tiempo real (RTP) es una característica de Microsoft Defender para Endpoint para Mac que supervisa y protege continuamente el dispositivo contra amenazas. Consiste en la supervisión de archivos y procesos y otras heurísticas.

Según las aplicaciones que ejecutes y las características del dispositivo, es posible que experimentes un rendimiento subóptimo al ejecutar Microsoft Defender para Endpoint para Mac. En particular, las aplicaciones o los procesos del sistema que tienen acceso a muchos recursos en un período de tiempo corto pueden provocar problemas de rendimiento en Microsoft Defender para Endpoint para Mac.

Se pueden usar los siguientes pasos para solucionar y mitigar estos problemas:

1. Deshabilite la protección en tiempo real con uno de los siguientes métodos y observe si el rendimiento mejora. Este enfoque ayuda a reducir si Microsoft Defender para Endpoint para Mac está contribuyendo a los problemas de rendimiento.

    Si su organización no administra el dispositivo, la protección en tiempo real se puede deshabilitar mediante una de las siguientes opciones:

    - Desde la interfaz de usuario. Abra Microsoft Defender para Endpoint para Mac y vaya a **Administrar la configuración**.

      ![Administrar la captura de pantalla de protección en tiempo real](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - Desde el terminal. Por motivos de seguridad, esta operación requiere elevación.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    Si su organización administra el dispositivo, el administrador puede deshabilitar la protección en tiempo real con las instrucciones de Establecer preferencias para [Microsoft Defender para](mac-preferences.md)Endpoint para Mac .

2. Abra Finder y vaya a  >  **Utilidades de aplicaciones**. Abra **El Monitor de** actividad y analice qué aplicaciones usan los recursos del sistema. Algunos ejemplos típicos son los actualizadores de software y los compiladores.

3. Configure Microsoft Defender para Endpoint para Mac con exclusiones para los procesos o ubicaciones de disco que contribuyen a los problemas de rendimiento y vuelva a habilitar la protección en tiempo real.

    Consulta [Configurar y validar exclusiones para Microsoft Defender para Endpoint para Mac](mac-exclusions.md) para obtener más información.
