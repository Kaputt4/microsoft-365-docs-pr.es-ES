---
title: Implementar Microsoft Defender para endpoint en Linux con Ansible
ms.reviewer: ''
description: Describe cómo implementar Microsoft Defender para Endpoint en Linux con Ansible.
keywords: microsoft, defender, Microsoft Defender para Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 9cd544ca3d714ea46c74e10f8aba5e46dc0e1b35
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280998"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Implementar Microsoft Defender para endpoint en Linux con Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

En este artículo se describe cómo implementar Defender for Endpoint en Linux mediante Ansible. Una implementación correcta requiere la finalización de todas las tareas siguientes:

- [Descargar el paquete de incorporación](#download-the-onboarding-package)
- [Crear archivos YAML ansibles](#create-ansible-yaml-files)
- [Implementación](#deployment)
- [References](#references)

## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

Antes de empezar, consulte la página principal defender para endpoint [en Linux](microsoft-defender-endpoint-linux.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.

Además, para la implementación de Ansible, debes familiarizarte con las tareas de administración de Ansible, configurar Ansible y saber cómo implementar libros de juegos y tareas. Ansible tiene muchas formas de completar la misma tarea. Estas instrucciones suponen la disponibilidad de módulos Ansible compatibles, como *aptos* y *norchivos* para ayudar a implementar el paquete. Su organización puede usar un flujo de trabajo diferente. Consulte la [documentación de Ansible](https://docs.ansible.com/) para obtener más información.

- Ansible debe instalarse en al menos un equipo (Ansible llama a este nodo de control).
- SSH debe configurarse para una cuenta de administrador entre el nodo de control y todos los nodos administrados (dispositivos que tendrán Instalado Defender for Endpoint) y se recomienda configurar con autenticación de clave pública.
- El siguiente software debe instalarse en todos los nodos administrados:
  - rizo
  - python-apt

- Todos los nodos administrados deben aparecer con el siguiente formato en el `/etc/ansible/hosts` archivo o correspondiente:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Prueba de ping:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Descargar el paquete de incorporación

Descargue el paquete de incorporación desde Centro de seguridad de Microsoft Defender:

1. En Centro de seguridad de Microsoft Defender, vaya **a Configuración > Device Management > Onboarding**.
2. En el primer menú desplegable, seleccione **Linux Server** como sistema operativo. En el segundo menú desplegable, seleccione **La herramienta de** administración de configuración de Linux preferida como método de implementación.
3. Seleccione **Descargar paquete de incorporación**. Guarde el archivo como WindowsDefenderATPOnboardingPackage.zip.

    ![Centro de seguridad de Microsoft Defender captura de pantalla](images/atp-portal-onboarding-linux-2.png)

4. Desde un símbolo del sistema, compruebe que tiene el archivo. Extraiga el contenido del archivo:

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a>Crear archivos YAML ansibles

Crea una subtarea o archivos de roles que contribuyan a un libro de juegos o una tarea.

- Cree la tarea de `onboarding_setup.yml` incorporación:

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- Agregue el repositorio y la clave defender para el extremo.

    Defender para Endpoint en Linux se puede implementar desde uno de los siguientes canales (que se indican a continuación como *[canal]):* *insiders-fast*, *insiders-slow* o *prod*. Cada uno de estos canales corresponde a un repositorio de software de Linux.

    La elección del canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen al dispositivo. Los dispositivos *de insiders-fast* son los primeros en recibir actualizaciones y nuevas características, seguidos más adelante por *insiders-slow* y, por último, por *prod*.

    Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa para que usen *insiders-fast* o *insiders-slow*.

    > [!WARNING]
    > Cambiar el canal después de la instalación inicial requiere que se vuelva a instalar el producto. Para cambiar el canal de producto: desinstale el paquete existente, vuelva a configurar el dispositivo para que use el nuevo canal y siga los pasos descritos en este documento para instalar el paquete desde la nueva ubicación.

    Tenga en cuenta la distribución y la versión e identifique la entrada más cercana para ella en `https://packages.microsoft.com/config/` .

    En los siguientes comandos, reemplace *[distro]* y *[version]* por la información que haya identificado.

    > [!NOTE]
    > En el caso de Oracle Linux, reemplace *[distro]* por "rhel".

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Cree los archivos YAML de instalación y desinstalación de Ansible.

    - Para las distribuciones basadas en apt, use el siguiente archivo YAML:

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - Para las distribuciones basadas en dnf, use el siguiente archivo YAML:

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a>Implementación

Ahora ejecute los archivos de tareas en `/etc/ansible/playbooks/` el directorio correspondiente o en el directorio correspondiente.

- Instalación:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Cuando el producto se inicia por primera vez, descarga las definiciones de antimalware más recientes. Según la conexión a Internet, esto puede tardar unos minutos.

- Validación/configuración:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- Desinstalación:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>Problemas de instalación del registro

Consulte [Problemas de instalación del registro](linux-resources.md#log-installation-issues) para obtener más información sobre cómo encontrar el registro generado automáticamente que crea el instalador cuando se produce un error.

## <a name="operating-system-upgrades"></a>Actualizaciones del sistema operativo

Al actualizar el sistema operativo a una nueva versión principal, primero debes desinstalar Defender para Endpoint en Linux, instalar la actualización y, por último, volver a configurar Defender para Endpoint en Linux en el dispositivo.

## <a name="references"></a>Referencias

- [Agregar o quitar repositorios de YUM](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Administrar paquetes con el administrador de paquetes dnf](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Agregar y quitar repositorios de APT](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Administrar paquetes aptos](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>Vea también
- [Investigar problemas de estado de agente](health-status.md)