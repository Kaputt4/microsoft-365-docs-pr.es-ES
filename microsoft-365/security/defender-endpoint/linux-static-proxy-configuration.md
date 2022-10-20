---
title: Microsoft Defender para punto de conexión en la detección de proxy estático de Linux
ms.reviewer: ''
description: Describe cómo configurar Microsoft Defender para punto de conexión en Linux para la detección de proxy estático.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, instalación, proxy
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
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: e58e81044e296f675c375e6caa5169e75eba51e6
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68622956"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>Configuración de Microsoft Defender para punto de conexión en Linux para la detección de proxy estático

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender para punto de conexión puede detectar un servidor proxy mediante la variable de `HTTPS_PROXY` entorno. Esta configuración debe configurarse **tanto** en el momento de la instalación como después de instalar el producto.

## <a name="installation-time-configuration"></a>Configuración del tiempo de instalación

Durante la instalación, la variable de `HTTPS_PROXY` entorno debe pasarse al administrador de paquetes. El administrador de paquetes puede leer esta variable de cualquiera de las maneras siguientes:

- La `HTTPS_PROXY` variable se define en `/etc/environment` con la línea siguiente:

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

- La `HTTPS_PROXY` variable se define en la configuración global del administrador de paquetes. Por ejemplo, en Ubuntu 18.04, puede agregar la siguiente línea a `/etc/apt/apt.conf.d/proxy.conf`:

  ```bash
  Acquire::https::Proxy "http://proxy.server:port/";
  ```

  > [!CAUTION]
  > Tenga en cuenta que los dos métodos anteriores podrían definir el proxy que se usará para otras aplicaciones del sistema. Use este método con precaución, o solo si está pensado para ser una configuración global general.

- La `HTTPS_PROXY` variable se antepone a los comandos de instalación o desinstalación. Por ejemplo, con el administrador de paquetes APT, anteponga la variable como se indica a continuación al instalar Microsoft Defender para punto de conexión:

  ```bash
  HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
  ```

  > [!NOTE]
  > No agregue sudo entre la definición de variable de entorno y apt; de lo contrario, la variable no se propagará.

La `HTTPS_PROXY` variable de entorno se puede definir de forma similar durante la desinstalación.

Tenga en cuenta que la instalación y desinstalación no producirán un error necesariamente si se requiere un proxy pero no está configurado. Sin embargo, la telemetría no se enviará y la operación podría tardar mucho más tiempo debido a los tiempos de espera de red.

## <a name="post-installation-configuration"></a>Configuración posterior a la instalación

Después de la instalación, configure Defender para punto de conexión con proxy estático mediante uno de los métodos siguientes:

```bash
mdatp config proxy set --value http://address:port
```
> [!NOTE]
> Este método funciona para cada distribución de Defender para punto de conexión en Linux y se **recomienda**.


La `HTTPS_PROXY` variable de entorno debe definirse en el archivo de servicio de Defender para punto de conexión. Para ello, ejecute `sudo systemctl edit --full mdatp.service`.
A continuación, puede propagar la variable al servicio de una de estas dos maneras:

- Quite la marca de comentario de la línea `#Environment="HTTPS_PROXY=http://address:port"` y especifique la dirección del proxy estático.

- Agregue una línea `EnvironmentFile=/path/to/env/file`. Esta ruta de acceso puede apuntar a o a `/etc/environment` un archivo personalizado, cualquiera de los cuales debe agregar la siguiente línea:

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

Después de `mdatp.service`modificar , guarde el archivo y reinicie el servicio para que los cambios se puedan aplicar mediante los siguientes comandos:

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```
> [!NOTE]
> Para quitar las adiciones que haya realizado antes de `mdatp`desinstalar , elimine el archivo personalizado de `/etc/systemd/system`.

> [!NOTE]
> Red Hat Enterprise Linux 6.X y CentOS 6.X no admiten los métodos **systemctl** y **/etc/environment** . Para configurar el proxy estático para MDE en estas distribuciones, use el método de **conjunto de proxy de configuración mdatp** recomendado.
