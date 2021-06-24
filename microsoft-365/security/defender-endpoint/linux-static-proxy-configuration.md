---
title: Detección de proxy estático de Microsoft Defender para endpoint en Linux
ms.reviewer: ''
description: Describe cómo configurar Microsoft Defender para Endpoint en Linux para la detección de proxy estático.
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, instalación, proxy
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6dca58070d21271ffc832bcd628679303736f99e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108145"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>Configurar Microsoft Defender para endpoint en Linux para la detección de proxy estático

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender para endpoint puede detectar un servidor proxy mediante la ```HTTPS_PROXY``` variable de entorno. Esta configuración debe configurarse **tanto en** el momento de la instalación como después de instalar el producto.

## <a name="installation-time-configuration"></a>Configuración de tiempo de instalación

Durante la instalación, la ```HTTPS_PROXY``` variable de entorno debe pasarse al administrador de paquetes. El administrador de paquetes puede leer esta variable de las siguientes maneras:

- La ```HTTPS_PROXY``` variable se define con la siguiente ```/etc/environment``` línea:

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- La `HTTPS_PROXY` variable se define en la configuración global del administrador de paquetes. Por ejemplo, en Ubuntu 18.04, puede agregar la siguiente línea a `/etc/apt/apt.conf.d/proxy.conf` :
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > Tenga en cuenta que los dos métodos anteriores podrían definir el proxy que se usará para otras aplicaciones del sistema. Use este método con precaución o solo si está pensado para ser una configuración global general.
  
- La `HTTPS_PROXY` variable se antepone a los comandos de instalación o desinstalación. Por ejemplo, con el administrador de paquetes de APT, anteponer la variable de la siguiente manera al instalar Microsoft Defender para endpoint: 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > No agregue sudo entre la definición de variable de entorno y apt, de lo contrario, la variable no se propagará.

La variable de entorno puede definirse de forma `HTTPS_PROXY` similar durante la desinstalación.

Tenga en cuenta que la instalación y desinstalación no necesariamente producirán errores si se requiere un proxy pero no está configurado. Sin embargo, la telemetría no se envía y la operación podría tardar mucho más tiempo debido a los tiempos de espera de la red.

## <a name="post-installation-configuration"></a>Configuración posterior a la instalación
  
Después de la instalación, `HTTPS_PROXY` la variable de entorno debe definirse en el archivo de servicio Defender for Endpoint. Para ello, abra `/lib/systemd/system/mdatp.service` en un editor de texto mientras se ejecuta como usuario raíz. A continuación, puede propagar la variable al servicio de dos maneras:

    > [!NOTE]
    > On CentOS or RedHat Linux distributions the location of the Endpoint service file is `/usr/lib/systemd/system/mdatp.service`.

- Descomprima la línea `#Environment="HTTPS_PROXY=http://address:port"` y especifica la dirección de proxy estática.

- Agregar una línea `EnvironmentFile=/path/to/env/file` . Esta ruta de acceso puede apuntar a o a un archivo personalizado, cualquiera de los `/etc/environment` cuales necesita agregar la siguiente línea:
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

Después de modificar el `mdatp.service` archivo, guárdelo y cierre. Reinicie el servicio para que se puedan aplicar los cambios. En Ubuntu, esto implica dos comandos:  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
