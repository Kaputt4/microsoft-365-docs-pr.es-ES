---
title: Solución de problemas de conectividad en la nube para Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Aprenda a solucionar problemas de conectividad en la nube para Microsoft Defender para punto de conexión en Linux
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, nube, conectividad, comunicación
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
ms.openlocfilehash: 2fd3e87fb6c93e640fa9939a2a23b4724f06f567
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521749"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Solución de problemas de conectividad en la nube para Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>Ejecución de la prueba de conectividad

Para probar si Defender para punto de conexión en Linux puede comunicarse con la nube con la configuración de red actual, ejecute una prueba de conectividad desde la línea de comandos:

```bash
mdatp connectivity test
```

salida esperada:

```output
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

Si se produce un error en la prueba de conectividad, compruebe si el dispositivo tiene acceso a Internet y si [alguno de los puntos de conexión requeridos por el producto](microsoft-defender-endpoint-linux.md#network-connections) está bloqueado por un proxy o firewall.

Los errores con el error de curl 35 o 60 indican el rechazo de anclaje de certificado. Compruebe si la conexión está bajo inspección SSL o HTTPS. Si es así, agregue Microsoft Defender para punto de conexión a la lista de permitidos.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>Pasos de solución de problemas para entornos sin proxy o con proxy transparente

Para probar que una conexión no está bloqueada en un entorno sin un proxy o con un proxy transparente, ejecute el siguiente comando en el terminal:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

La salida de este comando debe ser similar a:

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>Pasos de solución de problemas para entornos con proxy estático

> [!WARNING]
> No se admiten los servidores proxy PAC, WPAD y autenticados. Asegúrese de que solo se usa un proxy estático o un proxy transparente.
>
> Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad. Configure una excepción para la inspección ssl y el servidor proxy para pasar directamente los datos de Defender para punto de conexión en Linux a las direcciones URL pertinentes sin interceptación. Agregar el certificado de interceptación al almacén global no permitirá la interceptación.

Si se requiere un proxy estático, agregue un parámetro de proxy al comando anterior, donde `proxy_address:port` corresponde a la dirección y el puerto del proxy:

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Asegúrese de usar la misma dirección de proxy y puerto que se ha configurado en el `/lib/system/system/mdatp.service` archivo. Compruebe la configuración del proxy si hay errores de los comandos anteriores.

Para establecer el proxy para mdatp, use el siguiente comando:

```bash
mdatp config proxy set --value http://address:port 
```


Una vez realizado correctamente, intente otra prueba de conectividad desde la línea de comandos:

```bash
mdatp connectivity test
```

Si el problema persiste, póngase en contacto con el soporte al cliente.

## <a name="resources"></a>Recursos

- Para obtener más información sobre cómo configurar el producto para usar un proxy estático, consulte [Configuración de Microsoft Defender para punto de conexión para la detección de proxy estático](linux-static-proxy-configuration.md).
