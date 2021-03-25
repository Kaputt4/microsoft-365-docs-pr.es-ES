---
title: Implementar ATP de Microsoft Defender para Linux con Puppet
ms.reviewer: ''
description: Describe cómo implementar ATP de Microsoft Defender para Linux con Puppet.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 06611c19994ba34c4b59eb1a32b9ab9fd91cc1aa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074947"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-with-puppet"></a>Implementar Microsoft Defender para endpoint para Linux con Puppet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

En este artículo se describe cómo implementar Defender for Endpoint for Linux con Puppet. Una implementación correcta requiere la finalización de todas las tareas siguientes:

- [Descargar el paquete de incorporación](#download-the-onboarding-package)
- [Crear manifiesto de Puppet](#create-a-puppet-manifest)
- [Implementación](#deployment)
- [Comprobar el estado de incorporación](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

 Para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual, vea la página principal [defender para endpoint para Linux](microsoft-defender-endpoint-linux.md).

Además, para la implementación de Puppet, debes familiarizarte con las tareas de administración de Puppet, configurar Puppet y saber cómo implementar paquetes. Puppet tiene muchas maneras de completar la misma tarea. Estas instrucciones suponen la disponibilidad de módulos de Puppet compatibles, como *aptos* para ayudar a implementar el paquete. Su organización puede usar un flujo de trabajo diferente. Consulte la documentación [de Puppet](https://puppet.com/docs) para obtener más información.

## <a name="download-the-onboarding-package"></a>Descargar el paquete de incorporación

Descargue el paquete de incorporación del Centro de seguridad de Microsoft Defender:

1. En el Centro de seguridad de Microsoft Defender, vaya **a Configuración > Administración de dispositivos > incorporación**.
2. En el primer menú desplegable, seleccione **Linux Server** como sistema operativo. En el segundo menú desplegable, seleccione **La herramienta de** administración de configuración de Linux preferida como método de implementación.
3. Seleccione **Descargar paquete de incorporación**. Guarde el archivo como WindowsDefenderATPOnboardingPackage.zip.

    ![Captura de pantalla del Centro de seguridad de Microsoft Defender](images/atp-portal-onboarding-linux-2.png)

4. Desde un símbolo del sistema, compruebe que tiene el archivo. 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. Extraiga el contenido del archivo.
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a>Crear un manifiesto de Puppet

Debes crear un manifiesto de Puppet para implementar Defender para Endpoint para Linux en dispositivos administrados por un servidor Desatensado. En este ejemplo se usa los módulos *apt* y *yumrepo* disponibles en los puppetlabs y se supone que los módulos se han instalado en el servidor de Puppet.

Crea las *carpetas install_mdatp/archivos* *y install_mdatp/manifiestos* en la carpeta módulos de la instalación de Puppet. Esta carpeta normalmente se encuentra *en /etc/puppetlabs/code/environments/production/modules* en el servidor de Puppet. Copie el archivo mdatp_onboard.jsen creado anteriormente en la *carpeta install_mdatp/archivos.* Crear un *init.pp* que contiene las instrucciones de implementación:

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a>Contenido de `install_mdatp/manifests/init.pp`

Defender para Endpoint para Linux se puede implementar desde uno de los siguientes canales (que se indican a continuación como *[channel]):* *insiders-fast*, *insiders-slow* o *prod*. Cada uno de estos canales corresponde a un repositorio de software de Linux.

La elección del canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen al dispositivo. Los dispositivos *de insiders-fast* son los primeros en recibir actualizaciones y nuevas características, seguidos más adelante por *insiders-slow* y, por último, por *prod*.

Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa para que usen *insiders-fast* o *insiders-slow*.

> [!WARNING]
> Cambiar el canal después de la instalación inicial requiere que se vuelva a instalar el producto. Para cambiar el canal de producto: desinstale el paquete existente, vuelva a configurar el dispositivo para que use el nuevo canal y siga los pasos descritos en este documento para instalar el paquete desde la nueva ubicación.

Tenga en cuenta la distribución y la versión e identifique la entrada más cercana para ella en `https://packages.microsoft.com/config/` .

En los comandos siguientes, reemplace *[distro]* y *[version]* por la información que haya identificado:

> [!NOTE]
> En el caso de RedHat, Oracle EL y CentOS 8, reemplace *[distro]* por 'rhel'.

```puppet
# Puppet manifest to install Microsoft Defender ATP.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a>Implementación

Incluir el manifiesto anterior en su site.pp archivo:

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

Los dispositivos de agente inscritos sondean periódicamente el servidor de Puppet e instalan nuevos perfiles y directivas de configuración tan pronto como se detectan.

## <a name="monitor-puppet-deployment"></a>Supervisar la implementación de Puppet

En el dispositivo de agente, también puedes comprobar el estado de incorporación ejecutando:

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- **licencia:** esto confirma que el dispositivo está vinculado a su organización.

- **orgId:** este es el identificador de la organización Defender for Endpoint.

## <a name="check-onboarding-status"></a>Comprobar el estado de incorporación

Puedes comprobar que los dispositivos se han incorporado correctamente mediante la creación de un script. Por ejemplo, el siguiente script comprueba el estado de incorporación de los dispositivos inscritos:

```bash
mdatp health --field healthy
```

El comando anterior imprime si el producto está incorporado y `1` funciona según lo esperado.

> [!IMPORTANT]
> Cuando el producto se inicia por primera vez, descarga las definiciones de antimalware más recientes. Según la conexión a Internet, esto puede tardar unos minutos. Durante este tiempo, el comando anterior devuelve un valor de `0` .

Si el producto no está en buen estado, el código de salida (que se puede `echo $?` comprobar) indica el problema:

- 1 si el dispositivo aún no está incorporado.
- 3 si no se puede establecer la conexión con el demonio.

## <a name="log-installation-issues"></a>Problemas de instalación del registro

 Para obtener más información sobre cómo buscar el registro generado automáticamente por el instalador cuando se produce un error, vea [Log installation issues](linux-resources.md#log-installation-issues).

## <a name="operating-system-upgrades"></a>Actualizaciones del sistema operativo

Al actualizar el sistema operativo a una nueva versión principal, primero debes desinstalar Defender para Endpoint para Linux, instalar la actualización y, por último, volver a configurar Defender para Endpoint para Linux en el dispositivo.

## <a name="uninstallation"></a>Desinstalación

Crear un módulo *remove_mdatp* similar a *install_mdatp* con el siguiente contenido en *init.pp* archivo:

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
