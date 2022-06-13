---
title: Implementación de Microsoft Defender para punto de conexión en Linux con Puppet
ms.reviewer: ''
description: Describe cómo implementar Microsoft Defender para punto de conexión en Linux mediante Puppet.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos, fedora, amazon linux 2
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
ms.openlocfilehash: 9fe38f8bec7ca99d9c1828126382c8f70a22fa3a
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66014612"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a>Implementación de Microsoft Defender para punto de conexión en Linux con Puppet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

En este artículo se describe cómo implementar Defender para punto de conexión en Linux mediante Puppet. Una implementación correcta requiere la finalización de todas las tareas siguientes:

- [Descarga del paquete de incorporación](#download-the-onboarding-package)
- [Crear manifiesto de Puppet](#create-a-puppet-manifest)
- [Implementación](#deployment)
- [Comprobación del estado de incorporación](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

 Para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual, consulte [la página principal de Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md).

Además, para la implementación de Puppet, debe estar familiarizado con las tareas de administración de Puppet, tener Puppet configurado y saber cómo implementar paquetes. Puppet tiene muchas maneras de completar la misma tarea. Estas instrucciones asumen la disponibilidad de los módulos de Puppet compatibles, como *apt* para ayudar a implementar el paquete. Su organización podría usar un flujo de trabajo diferente. Consulte la [documentación de Puppet](https://puppet.com/docs) para obtener más información.

## <a name="download-the-onboarding-package"></a>Descarga del paquete de incorporación

Descargue el paquete de incorporación desde Microsoft 365 Defender portal:

1. En Microsoft 365 Defender portal, vaya a **Configuración > Puntos de conexión > Administración de dispositivos > Incorporación**.
2. En el primer menú desplegable, seleccione **Servidor Linux** como sistema operativo. En el segundo menú desplegable, seleccione **La herramienta de administración de configuración de Linux preferida** como método de implementación.
3. Seleccione **Descargar el paquete de incorporación** Guarde el archivo como WindowsDefenderATPOnboardingPackage.zip.

   :::image type="content" source="images/portal-onboarding-linux-2.png" alt-text="La opción para descargar el paquete incorporado" lightbox="images/portal-onboarding-linux-2.png":::

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

## <a name="create-a-puppet-manifest"></a>Creación de un manifiesto de Puppet

Debe crear un manifiesto de Puppet para implementar Defender para punto de conexión en Linux en dispositivos administrados por un servidor de Puppet. En este ejemplo se hace uso de los módulos *apt* y *yumrepo* disponibles en puppetlabs y se supone que los módulos se han instalado en el servidor de Puppet.

Cree las carpetas *install_mdatp/files* y *install_mdatp/manifests* en la carpeta modules de la instalación de Puppet. Esta carpeta se encuentra normalmente en */etc/puppetlabs/code/environments/production/modules* en el servidor de Puppet. Copie el archivo mdatp_onboard.json creado anteriormente en la carpeta *install_mdatp/files* . Creación de un *archivo init.pp* archivo que contiene las instrucciones de implementación:

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

Defender para punto de conexión en Linux se puede implementar desde uno de los siguientes canales (que se indica a continuación como *[canal]*): *insiders-fast*, *insiders-slow* o *prod*. Cada uno de estos canales corresponde a un repositorio de software linux.

La elección del canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen al dispositivo. Los dispositivos de *insiders-fast* son los primeros en recibir actualizaciones y nuevas características, seguidos más adelante por *los usuarios internos lentos* y, por último, por *producción*.

Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa para usar *insiders-fast* o *insiders-slow*.

> [!WARNING]
> Cambiar el canal después de la instalación inicial requiere que se vuelva a instalar el producto. Para cambiar el canal del producto: desinstale el paquete existente, vuelva a configurar el dispositivo para que use el nuevo canal y siga los pasos de este documento para instalar el paquete desde la nueva ubicación.

Anote la distribución y la versión e identifique la entrada más cercana en `https://packages.microsoft.com/config/[distro]/`.

En los comandos siguientes, reemplace *[distro]* y *[version]* por la información que ha identificado:

> [!NOTE]
> En el caso de RedHat, Oracle Linux, Amazon Linux 2 y CentOS 8, reemplace *[distro]* por 'rhel'.

```puppet
# Puppet manifest to install Microsoft Defender for Endpoint on Linux.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle Linux, Amazon Linux 2, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
        $release = $channel ? {
        'prod' => $facts['os']['distro']['codename']
        default => $channel
        }
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  =>  $release,
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

Incluir el manifiesto anterior en el sitio.pp Archivo:

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```

```Output
node "default" {
    include install_mdatp
}
```

Los dispositivos de agente inscritos sondean periódicamente Puppet Server e instalan nuevos perfiles de configuración y directivas en cuanto se detectan.

## <a name="monitor-puppet-deployment"></a>Supervisión de la implementación de Puppet

En el dispositivo del agente, también puede comprobar el estado de incorporación ejecutando:

```bash
mdatp health
```

```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- **con licencia**: esto confirma que el dispositivo está asociado a su organización.

- **orgId**: este es el identificador de la organización de Defender para punto de conexión.

## <a name="check-onboarding-status"></a>Comprobación del estado de incorporación

Puede comprobar que los dispositivos se han incorporado correctamente mediante la creación de un script. Por ejemplo, el siguiente script comprueba el estado de incorporación de los dispositivos inscritos:

```bash
mdatp health --field healthy
```

El comando anterior imprime `1` si el producto está incorporado y funciona según lo esperado.

> [!IMPORTANT]
> Cuando el producto se inicia por primera vez, descarga las definiciones de antimalware más recientes. Dependiendo de la conexión a Internet, esto puede tardar hasta unos minutos. Durante este tiempo, el comando anterior devuelve un valor de `0`.

Si el producto no es correcto, el código de salida (que se puede comprobar a través `echo $?`de ) indica el problema:

- 1 si el dispositivo aún no está incorporado.
- 3 si no se puede establecer la conexión con el demonio.

## <a name="log-installation-issues"></a>Problemas de instalación de registros

 Para obtener más información sobre cómo buscar el registro generado automáticamente que crea el instalador cuando se produce un error, consulte [Problemas de instalación de registros](linux-resources.md#log-installation-issues).

## <a name="operating-system-upgrades"></a>Actualizaciones del sistema operativo

Al actualizar el sistema operativo a una nueva versión principal, primero debe desinstalar Defender para punto de conexión en Linux, instalar la actualización y, por último, volver a configurar Defender para punto de conexión en Linux en el dispositivo.

## <a name="uninstallation"></a>Desinstalación

Cree un módulo *remove_mdatp* similar a *install_mdatp* con el siguiente contenido en *init.pp.* Archivo:

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
