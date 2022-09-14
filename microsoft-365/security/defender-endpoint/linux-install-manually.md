---
title: Implementación manual de Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Describe cómo implementar Microsoft Defender para punto de conexión en Linux manualmente desde la línea de comandos.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos, fedora, amazon linux 2
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
ms.openlocfilehash: 5a388e6e7dc38a91b995ef90498c58326fee7e91
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67688019"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a>Implementación manual de Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

En este artículo se describe cómo implementar manualmente Microsoft Defender para punto de conexión en Linux. Una implementación correcta requiere la finalización de todas las tareas siguientes:

- [Requisitos previos y requisitos del sistema](#prerequisites-and-system-requirements)
- [Configuración del repositorio de software linux](#configure-the-linux-software-repository)
  - [RHEL y variantes (CentOS, Fedora, Oracle Linux y Amazon Linux 2)](#rhel-and-variants-centos-fedora-oracle-linux-and-amazon-linux-2)
  - [SLES y variantes](#sles-and-variants)
  - [Sistemas Ubuntu y Debian](#ubuntu-and-debian-systems)
- [Instalación de la aplicación](#application-installation)
- [Descarga del paquete de incorporación](#download-the-onboarding-package)
- [Configuración del cliente](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

Antes de empezar, consulte [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.

> [!WARNING]
> La actualización del sistema operativo a una nueva versión principal después de la instalación del producto requiere la reinstalación del producto. Debe [desinstalar](linux-resources.md#uninstall) defender para punto de conexión existente en Linux, actualizar el sistema operativo y, a continuación, volver a configurar Defender para punto de conexión en Linux siguiendo los pasos siguientes.

## <a name="configure-the-linux-software-repository"></a>Configuración del repositorio de software linux

Defender para punto de conexión en Linux se puede implementar desde uno de los siguientes canales (que se indica a continuación como *[canal]*): *insiders-fast*, *insiders-slow* o *prod*. Cada uno de estos canales corresponde a un repositorio de software linux. A continuación se proporcionan instrucciones para configurar el dispositivo para usar uno de estos repositorios.

La elección del canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen al dispositivo. Los dispositivos de *insiders-fast* son los primeros en recibir actualizaciones y nuevas características, seguidos más adelante por *los usuarios internos lentos* y, por último, por *producción*.

Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa para usar *insiders-fast* o *insiders-slow*.

> [!WARNING]
> Cambiar el canal después de la instalación inicial requiere que se vuelva a instalar el producto. Para cambiar el canal del producto: desinstale el paquete existente, vuelva a configurar el dispositivo para que use el nuevo canal y siga los pasos de este documento para instalar el paquete desde la nueva ubicación.

### <a name="rhel-and-variants-centos-fedora-oracle-linux-and-amazon-linux-2"></a>RHEL y variantes (CentOS, Fedora, Oracle Linux y Amazon Linux 2)

- Instale `yum-utils` si aún no está instalado:

    ```bash
    sudo yum install yum-utils
    ```

  > [!NOTE]
  > La distribución y la versión, e identificar la entrada más cercana (por principal y, a continuación, secundaria) en `https://packages.microsoft.com/config/rhel/`.

    Use la tabla siguiente para ayudarle a localizar el paquete:

    |Distro & versión|Paquete|
    |---|---|
    |Para RHEL/Centos/Oracle 8.0-8.5|<https://packages.microsoft.com/config/rhel/8/prod.repo>|
    |Para RHEL/Centos/Oracle 7.2-7.9 & Amazon Linux 2 |<https://packages.microsoft.com/config/rhel/7.2/prod.repo>|
    |Para Fedora 33|<https://packages.microsoft.com/config/fedora/33/prod.repo>|
    |Para Fedora 34|<https://packages.microsoft.com/config/fedora/34/prod.repo>|

    <!--|For RHEL/Centos 6.7-6.10|<https://packages.microsoft.com/config/rhel/6/[channel].repo>|-->

    En los siguientes comandos, reemplace *[version]* y *[channel]* por la información que ha identificado:

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/rhel/[version]/[channel].repo
    ```

    > [!TIP]
    > Use el comando hostnamectl para identificar la información relacionada con el sistema, incluida la versión *[versión]*.

    Por ejemplo, si ejecuta CentOS 7 y desea implementar Defender para punto de conexión en Linux desde el canal de *prod* :

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/rhel/7/prod.repo
    ```

    O bien, si desea explorar nuevas características en dispositivos seleccionados, es posible que quiera implementar Microsoft Defender para punto de conexión en Linux en el canal *rápido de insiders*:

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/rhel/7/insiders-fast.repo
    ```

- Instale la clave pública de Microsoft GPG:

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="sles-and-variants"></a>SLES y variantes

> [!NOTE]
> La distribución y la versión, e identificar la entrada más cercana (por principal y, a continuación, secundaria) en `https://packages.microsoft.com/config/sles/`.

   En los comandos siguientes, reemplace *[distro]* y *[version]* por la información que ha identificado:

   ```bash
   sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
   ```

   > [!TIP]
   > Use el comando SPident para identificar la información relacionada con el sistema, incluida la versión *[versión]*.

   Por ejemplo, si ejecuta SLES 12 y desea implementar Microsoft Defender para punto de conexión en Linux desde el canal de *producción*:

   ```bash
   sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
   ```

- Instale la clave pública de Microsoft GPG:

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a>Sistemas Ubuntu y Debian

- Instale `curl` si aún no está instalado:

    ```bash
    sudo apt-get install curl
    ```

- Instale `libplist-utils` si aún no está instalado:

    ```bash
    sudo apt-get install libplist-utils
    ```

> [!NOTE]
> La distribución y la versión, e identificar la entrada más cercana (por principal y, a continuación, secundaria) en `https://packages.microsoft.com/config/[distro]/`.

   En el siguiente comando, reemplace *[distro]* y *[version]* por la información que ha identificado:

   ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
   ```

   > [!TIP]
   > Use el comando hostnamectl para identificar la información relacionada con el sistema, incluida la versión *[versión]*.

   Por ejemplo, si ejecuta Ubuntu 18.04 y desea implementar Microsoft Defender para punto de conexión en Linux desde el canal de *prod*:

   ```bash
   curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
   ```

- Instale la configuración del repositorio:

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```

    Por ejemplo, si elige *prod* channel:

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- Instale el `gpg` paquete si aún no está instalado:

    ```bash
    sudo apt-get install gpg
    ```

  Si `gpg` no está disponible, instale `gnupg`.

    ```bash
    sudo apt-get install gnupg
    ```

- Instale la clave pública de Microsoft GPG:

    ```bash
    curl -sSL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null
    ```

- Instale el controlador HTTPS si aún no está instalado:

    ```bash
    sudo apt-get install apt-transport-https
    ```

- Actualice los metadatos del repositorio:

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a>Instalación de la aplicación

- RHEL y variantes (CentOS y Oracle Linux):

    ```bash
    sudo yum install mdatp
    ```

    > [!NOTE]
    > Si tiene varios repositorios de Microsoft configurados en el dispositivo, puede ser específico sobre desde qué repositorio instalar el paquete. En el ejemplo siguiente se muestra cómo instalar el paquete desde el `production` canal si también tiene el canal del `insiders-fast` repositorio configurado en este dispositivo. Esta situación puede ocurrir si usa varios productos de Microsoft en el dispositivo. En función de la distribución y la versión del servidor, el alias del repositorio podría ser diferente al del ejemplo siguiente.

    ```bash
    # list all repositories
    yum repolist
    ```

    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```

    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- SLES y variantes:

    ```bash
    sudo zypper install mdatp
    ```

    > [!NOTE]
    > Si tiene varios repositorios de Microsoft configurados en el dispositivo, puede ser específico sobre desde qué repositorio instalar el paquete. En el ejemplo siguiente se muestra cómo instalar el paquete desde el `production` canal si también tiene el canal del `insiders-fast` repositorio configurado en este dispositivo. Esta situación puede ocurrir si usa varios productos de Microsoft en el dispositivo.

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...

    ```

    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- Sistema Ubuntu y Debian:

    ```bash
    sudo apt-get install mdatp
    ```

    > [!NOTE]
    > Si tiene varios repositorios de Microsoft configurados en el dispositivo, puede ser específico sobre desde qué repositorio instalar el paquete. En el ejemplo siguiente se muestra cómo instalar el paquete desde el `production` canal si también tiene el canal del `insiders-fast` repositorio configurado en este dispositivo. Esta situación puede ocurrir si usa varios productos de Microsoft en el dispositivo.

    ```bash
    cat /etc/apt/sources.list.d/*
    ```

    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/config/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/config/ubuntu/18.04/prod bionic main
    ```

    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a>Descarga del paquete de incorporación

Descargue el paquete de incorporación desde Microsoft 365 Defender portal.

> [!IMPORTANT]
> Si se pierde este paso, cualquier comando ejecutado mostrará un mensaje de advertencia que indica que el producto no tiene licencia. Además, el `mdatp health` comando devuelve un valor de `false`.

1. En el portal de Microsoft 365 Defender, vaya a **Configuración > puntos de conexión > Administración de dispositivos > Incorporación**.
2. En el primer menú desplegable, seleccione **Servidor Linux** como sistema operativo. En el segundo menú desplegable, seleccione **Script local** como método de implementación.
3. Seleccione **Descargar el paquete de incorporación** Guarde el archivo como WindowsDefenderATPOnboardingPackage.zip.

   :::image type="content" source="images/portal-onboarding-linux.png" alt-text="Descarga de un paquete de incorporación en el portal de Microsoft 365 Defender" lightbox="images/portal-onboarding-linux.png":::

4. Desde un símbolo del sistema, compruebe que tiene el archivo y extraiga el contenido del archivo:

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```

    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

## <a name="client-configuration"></a>Configuración de clientes

1. Copie MicrosoftDefenderATPOnboardingLinuxServer.py en el dispositivo de destino.

    > [!NOTE]
    > Inicialmente, el dispositivo cliente no está asociado a una organización y el atributo *orgId* está en blanco.

    ```bash
    mdatp health --field org_id
    ```

2. Ejecute MicrosoftDefenderATPOnboardingLinuxServer.py.

    > [!NOTE]
    > Para ejecutar este comando, debe tener `python`  o `python3` instalar en el dispositivo en función de la versión y la disto. Si es necesario, consulte [Instrucciones paso a paso para instalar Python en Linux](https://opensource.com/article/20/4/install-python-linux).

    Si ejecuta RHEL 8.x o Ubuntu 20.04 o posterior, deberá usar `python3`.

    ```bash
    sudo python3 MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

    Para el resto de distribuciones y versiones, deberá usar `python`.

    ```bash
    sudo python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. Compruebe que el dispositivo ahora está asociado a su organización e informa de un identificador de organización válido:

    ```bash
    mdatp health --field org_id
    ```

4. Compruebe el estado de mantenimiento del producto ejecutando el siguiente comando. Un valor devuelto de `1` indica que el producto funciona según lo esperado:

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > Cuando el producto se inicia por primera vez, descarga las definiciones de antimalware más recientes. Esto puede tardar hasta unos minutos en función de la conectividad de red. Durante este tiempo, el comando anterior devuelve un valor de `false`. Puede comprobar el estado de la actualización de definición mediante el siguiente comando:
    >
    > ```bash
    > mdatp health --field definitions_status
    > ```
    >
    > Tenga en cuenta que es posible que también tenga que configurar un proxy después de completar la instalación inicial. Consulte [Configuración de Defender para punto de conexión en Linux para la detección de proxy estático: configuración posterior a la instalación](linux-static-proxy-configuration.md#post-installation-configuration).

5. Ejecute una prueba de detección de ANTIVIRUS para comprobar que el dispositivo está incorporado correctamente e informar al servicio. Realice los pasos siguientes en el dispositivo recién incorporado:

    - Asegúrese de que la protección en tiempo real está habilitada (indicada por el resultado de la ejecución del `1` siguiente comando):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

      Si no está habilitado, ejecute el siguiente comando:

       ```bash
        mdatp config real-time-protection --value enabled
        ```

    - Abra una ventana terminal y ejecute el siguiente comando:

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - Defender para punto de conexión en Linux debería haber puesto en cuarentena el archivo. Use el siguiente comando para enumerar todas las amenazas detectadas:

        ```bash
        mdatp threat list
        ```

6. Ejecute una prueba de detección de EDR y simule una detección para comprobar que el dispositivo está incorporado correctamente e informar al servicio. Realice los pasos siguientes en el dispositivo recién incorporado:

    - Compruebe que el servidor Linux incorporado aparece en Microsoft 365 Defender. Si se trata de la primera incorporación de la máquina, puede tardar hasta 20 minutos en aparecer.

    - Descargue y extraiga el [archivo de script](https://aka.ms/LinuxDIY) en un servidor Linux incorporado y ejecute el siguiente comando: `./mde_linux_edr_diy.sh`

    - Después de unos minutos, se debe generar una detección en Microsoft 365 Defender.

    - Examine los detalles de la alerta, la escala de tiempo de la máquina y realice los pasos de investigación típicos.

## <a name="installer-script"></a>Script del instalador

Como alternativa, puede usar un [script de bash del instalador](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) automatizado proporcionado en nuestro [repositorio público de GitHub](https://github.com/microsoft/mdatp-xplat/).
El script identifica la distribución y la versión, simplifica la selección del repositorio adecuado, configura el dispositivo para extraer el paquete más reciente y combina los pasos de instalación e incorporación del producto.

```bash
> ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

Obtenga más [información aquí](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).

## <a name="log-installation-issues"></a>Problemas de instalación de registros

Consulte [Problemas de instalación](linux-resources.md#log-installation-issues) de registros para obtener más información sobre cómo buscar el registro generado automáticamente que crea el instalador cuando se produce un error.

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a>Migración de Insiders-Fast al canal de producción

1. Desinstale la versión "Canal Insiders-Fast" de Defender para punto de conexión en Linux.

    ```bash
    sudo yum remove mdatp
    ```

1. Deshabilitación del repositorio de Insiders-Fast de Defender para punto de conexión en Linux

    ```bash
    sudo yum repolist
    ```

    > [!NOTE]
    > La salida debe mostrar "packages-microsoft-com-fast-prod".

    ```bash
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ```

1. Vuelva a implementar Microsoft Defender para punto de conexión en Linux mediante el "canal de producción".

## <a name="uninstallation"></a>Desinstalación

Consulte [Desinstalación](linux-resources.md#uninstall) para obtener más información sobre cómo quitar Defender para punto de conexión en Linux de los dispositivos cliente.

## <a name="see-also"></a>Vea también

- [Investigar problemas de estado del agente](health-status.md)
