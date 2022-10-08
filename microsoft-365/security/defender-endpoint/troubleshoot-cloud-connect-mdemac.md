---
title: Solución de problemas de conectividad en la nube para Microsoft Defender para punto de conexión en macOS
description: En este tema se describe cómo solucionar problemas de conectividad en la nube para Microsoft Defender para punto de conexión en macOS
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 55c3e0376094ace126c775afa9f47f349e0eff90
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227710"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solución de problemas de conectividad en la nube para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataforma** macOS

En este tema se describe cómo solucionar problemas de conectividad en la nube para Microsoft Defender para punto de conexión en macOS.

## <a name="run-the-connectivity-test"></a>Ejecución de la prueba de conectividad
Para probar si Defender para punto de conexión en Mac puede comunicarse con la nube con la configuración de red actual, ejecute una prueba de conectividad desde la línea de comandos:

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

Si se produce un error en la prueba de conectividad, compruebe si el dispositivo tiene acceso a Internet y si [alguno de los puntos de conexión requeridos por el producto](microsoft-defender-endpoint-mac.md#network-connections) está bloqueado por un proxy o firewall.

Los errores con el error de curl 35 o 60 indican el rechazo de anclaje de certificados, lo que indica un posible problema con la inspección SSL o HTTPS. Consulte las instrucciones siguientes sobre la configuración de inspección SSL.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>Pasos de solución de problemas para entornos sin proxy o con configuración automática de proxy (PAC) o con protocolo de detección automática de proxy web (WPAD)
Use el procedimiento siguiente para probar que una conexión no está bloqueada en un entorno sin un proxy o con configuración automática de proxy (PAC) o con el Protocolo de detección automática de proxy web (WPAD).

Si un proxy o firewall bloquea el tráfico anónimo, asegúrese de que se permite el tráfico anónimo en las direcciones URL enumeradas anteriormente.

> [!WARNING]
> No se admiten servidores proxy autenticados. Asegúrese de que solo se usa PAC, WPAD o un proxy estático. Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad. Configure una excepción para la inspección SSL y el servidor proxy para pasar directamente los datos de Microsoft Defender para punto de conexión en macOS a las direcciones URL pertinentes sin interceptación. Agregar el certificado de interceptación al almacén global no permitirá la interceptación.
Para probar que una conexión no está bloqueada: en un explorador como Microsoft Edge para Mac o Safari, abra https://x.cp.wd.microsoft.com/api/report y https://cdn.x.cp.wd.microsoft.com/ping.

Opcionalmente, en Terminal, ejecute el siguiente comando:

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

La salida de este comando debe ser similar a:
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
