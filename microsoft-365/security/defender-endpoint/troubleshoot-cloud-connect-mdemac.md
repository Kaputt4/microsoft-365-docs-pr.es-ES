---
title: Solucionar problemas de conectividad en la nube para Microsoft Defender para endpoint en macOS
description: En este tema se describe cómo solucionar problemas de conectividad en la nube para Microsoft Defender para endpoint en macOS
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, instalación, implementación, desinstalación, intune, jamf, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 677737f530e35ed52a2a1f3fe7a8d6f18c26e7b6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326574"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solucionar problemas de conectividad en la nube para Microsoft Defender para endpoint en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataforma** macOS

En este tema se describe cómo solucionar problemas de conectividad en la nube para Microsoft Defender para endpoint en macOS.

## <a name="run-the-connectivity-test"></a>Ejecutar la prueba de conectividad
Para probar si Defender para Endpoint en Mac se puede comunicar a la nube con la configuración de red actual, ejecute una prueba de conectividad desde la línea de comandos:

```Bash
mdatp connectivity test
```

salida esperada:
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

Si se produce un error en la prueba de conectividad, compruebe si el dispositivo tiene acceso a Internet y si alguno de los puntos de conexión [requeridos](microsoft-defender-endpoint-mac.md#network-connections) por el producto está bloqueado por un proxy o firewall.

Los errores con error de curva 35 o 60 indican el rechazo de anclado de certificado, lo que indica un posible problema con la inspección SSL o HTTPS. Vea las instrucciones siguientes sobre la configuración de inspección SSL.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>Pasos de solución de problemas para entornos sin proxy o con proxy autoconfig (PAC) o con protocolo de detección automática de proxy web (WPAD)
Use el siguiente procedimiento para probar que una conexión no está bloqueada en un entorno sin un proxy o con proxy autoconfig (PAC) o con el Protocolo de detección automática de proxy web (WPAD).

Si un proxy o firewall bloquea el tráfico anónimo, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas anteriormente.

> [!WARNING]
> No se admiten servidores proxy autenticados. Asegúrese de que solo se usa PAC, WPAD o un proxy estático. Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad. Configure una excepción para que la inspección SSL y el servidor proxy pasen directamente los datos de Microsoft Defender para endpoint en macOS a las direcciones URL relevantes sin interceptación. Agregar el certificado de interceptación al almacén global no permitirá la interceptación.
Para probar que una conexión no está bloqueada: en un explorador como Microsoft Edge para Mac o Safari abierto https://x.cp.wd.microsoft.com/api/report y https://cdn.x.cp.wd.microsoft.com/ping.

Opcionalmente, en Terminal, ejecute el siguiente comando:

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

El resultado de este comando debe ser similar a:
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
