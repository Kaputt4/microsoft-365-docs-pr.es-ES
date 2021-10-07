---
title: Solucionar problemas de conectividad en la nube para Microsoft Defender para Endpoint en Linux
ms.reviewer: ''
description: Solucionar problemas de conectividad en la nube para Microsoft Defender para Endpoint en Linux
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, nube, conectividad, comunicación
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cbd0e45a44f3053e48b3714bb526e70d5d634502
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211002"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Solucionar problemas de conectividad en la nube para Microsoft Defender para Endpoint en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>Ejecutar la prueba de conectividad

Para probar si Defender for Endpoint en Linux puede comunicarse con la nube con la configuración de red actual, ejecute una prueba de conectividad desde la línea de comandos:

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

Si se produce un error en la prueba de conectividad, compruebe si el dispositivo tiene acceso a Internet y si alguno de los puntos de conexión [requeridos](microsoft-defender-endpoint-linux.md#network-connections) por el producto está bloqueado por un proxy o firewall.

Los errores con error de curva 35 o 60 indican el rechazo de anclado de certificado. Compruebe si la conexión está bajo inspección SSL o HTTPS. Si es así, agrega Microsoft Defender para Endpoint a la lista de permitidos.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>Pasos de solución de problemas para entornos sin proxy o con proxy transparente

Para probar que una conexión no está bloqueada en un entorno sin un proxy o con un proxy transparente, ejecute el siguiente comando en el terminal:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

El resultado de este comando debe ser similar a:

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>Pasos de solución de problemas para entornos con proxy estático

> [!WARNING]
> Pac, WPAD y proxies autenticados no son compatibles. Asegúrese de que solo se usa un proxy estático o un proxy transparente.
>
> Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad. Configure una excepción para la inspección SSL y el servidor proxy para pasar directamente los datos de Defender para Endpoint en Linux a las direcciones URL relevantes sin interceptación. Agregar el certificado de interceptación al almacén global no permitirá la interceptación.

Si se requiere un proxy estático, agregue un parámetro de proxy al comando anterior, donde corresponda a la dirección `proxy_address:port` y el puerto de proxy:

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Asegúrese de usar la misma dirección de proxy y el mismo puerto configurados en el `/lib/system/system/mdatp.service` archivo. Compruebe la configuración de proxy si hay errores de los comandos anteriores.

> [!WARNING]
> El proxy estático no se puede configurar a través de una variable de entorno en `HTTPS_PROXY` todo el sistema. En su lugar, `HTTPS_PROXY` asegúrese de que está correctamente establecido en el `/lib/system/system/mdatp.service` archivo.

Para usar un proxy estático, se `mdatp.service` debe modificar el archivo. Asegúrese de que `#` el inicial se quita para descomprimir la siguiente línea de `/lib/systemd/system/mdatp.service` :

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

Asegúrese también de que la dirección de proxy estática correcta esté rellenada para reemplazar `address:port` .

Si este archivo es correcto, intente ejecutar el siguiente comando en el terminal para volver a cargar Defender para Endpoint en Linux y propagar la configuración:

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

Una vez que se ha hecho correctamente, intente otra prueba de conectividad desde la línea de comandos:

```bash
mdatp connectivity test
```

Si el problema persiste, póngase en contacto con el servicio de soporte al cliente.

## <a name="resources"></a>Recursos

- Para obtener más información acerca de cómo configurar el producto para que use un proxy estático, vea [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).
