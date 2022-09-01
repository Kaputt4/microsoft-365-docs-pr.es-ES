---
title: Implementación de Microsoft Defender para punto de conexión en Linux con Ansible
ms.reviewer: ''
description: Describe cómo implementar Microsoft Defender para punto de conexión en Linux mediante Ansible.
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
ms.openlocfilehash: a35c50a941c7398c2c0722233627fe76f36f6afe
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522089"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Implementación de Microsoft Defender para punto de conexión en Linux con Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

En este artículo se describe cómo implementar Defender para punto de conexión en Linux mediante Ansible. Una implementación correcta requiere la finalización de todas las tareas siguientes:

- [Descarga del paquete de incorporación](#download-the-onboarding-package)
- [Creación de archivos YAML de Ansible](#create-ansible-yaml-files)
- [Implementación](#deployment)
- [Referencias](#references)

## <a name="prerequisites-and-system-requirements"></a>Requisitos previos y requisitos del sistema

Antes de empezar, consulte [la página principal de Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.

Además, para la implementación de Ansible, debe estar familiarizado con las tareas de administración de Ansible, tener Ansible configurado y saber cómo implementar cuadernos de estrategias y tareas. Ansible tiene muchas maneras de completar la misma tarea. Estas instrucciones asumen la disponibilidad de los módulos de Ansible admitidos, como *apt* y *unarchive* para ayudar a implementar el paquete. Su organización podría usar un flujo de trabajo diferente. Consulte la [documentación de Ansible](https://docs.ansible.com/) para obtener más información.

- Ansible debe instalarse en al menos un equipo (Ansible llama a este nodo de control).
- SSH debe configurarse para una cuenta de administrador entre el nodo de control y todos los nodos administrados (dispositivos que tendrán Defender para punto de conexión instalado en ellos) y se recomienda configurarlo con autenticación de clave pública.
- El software siguiente debe instalarse en todos los nodos administrados:
  - Enrollamiento
  - python-apt

- Todos los nodos administrados deben aparecer en el siguiente formato en el archivo o en el `/etc/ansible/hosts` archivo correspondiente:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Prueba de ping:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Descarga del paquete de incorporación

Descargue el paquete de incorporación desde Microsoft 365 Defender portal:

1. En Microsoft 365 Defender portal, vaya a **Configuración > puntos de conexión > Administración de dispositivos > Incorporación**.
2. En el primer menú desplegable, seleccione **Servidor Linux** como sistema operativo. En el segundo menú desplegable, seleccione **La herramienta de administración de configuración de Linux preferida** como método de implementación.
3. Seleccione **Descargar el paquete de incorporación** Guarde el archivo como WindowsDefenderATPOnboardingPackage.zip.

   :::image type="content" source="images/portal-onboarding-linux-2.png" alt-text="La opción Descargar paquete de incorporación" lightbox="images/portal-onboarding-linux-2.png":::

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

## <a name="create-ansible-yaml-files"></a>Creación de archivos YAML de Ansible

Cree una subtarea o archivos de roles que contribuyan a un cuaderno de estrategias o una tarea.

- Cree la tarea de incorporación, `onboarding_setup.yml`:

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

- Agregue el repositorio y la clave de Defender para punto de conexión, `add_apt_repo.yml`:

    Defender para punto de conexión en Linux se puede implementar desde uno de los siguientes canales (que se indica a continuación como *[canal]*): *insiders-fast*, *insiders-slow* o *prod*. Cada uno de estos canales corresponde a un repositorio de software linux.

    La elección del canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen al dispositivo. Los dispositivos de *insiders-fast* son los primeros en recibir actualizaciones y nuevas características, seguidos más adelante por *los usuarios internos lentos* y, por último, por *producción*.

    Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa para usar *insiders-fast* o *insiders-slow*.

    > [!WARNING]
    > Cambiar el canal después de la instalación inicial requiere que se vuelva a instalar el producto. Para cambiar el canal del producto: desinstale el paquete existente, vuelva a configurar el dispositivo para que use el nuevo canal y siga los pasos de este documento para instalar el paquete desde la nueva ubicación.

    Anote la distribución y la versión e identifique la entrada más cercana en `https://packages.microsoft.com/config/[distro]/`.

    En los comandos siguientes, reemplace *[distro]* y *[version]* por la información que ha identificado.

    > [!NOTE]
    > En el caso de Oracle Linux y Amazon Linux 2, reemplace *[distro]* por "rhel". Para Amazon Linux 2, reemplace *[versión]* por "7". Para el uso de Oracle, reemplace *[versión]* por la versión de Oracle Linux.

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      url: https://packages.microsoft.com/keys/microsoft.asc
      state: present
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [codename] main
      update_cache: yes
      state: present
      filename: microsoft-[channel]
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/ 
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Cree la instalación de Ansible y desinstale los archivos YAML.

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
                enablerepo: packages-microsoft-[channel]
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

Ahora ejecute los archivos de tareas en `/etc/ansible/playbooks/` el directorio correspondiente o .

- Instalación:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Cuando el producto se inicia por primera vez, descarga las definiciones de antimalware más recientes. Dependiendo de la conexión a Internet, esto puede tardar hasta unos minutos.

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

## <a name="log-installation-issues"></a>Problemas de instalación de registros

Consulte [Problemas de instalación](linux-resources.md#log-installation-issues) de registros para obtener más información sobre cómo buscar el registro generado automáticamente que crea el instalador cuando se produce un error.

## <a name="operating-system-upgrades"></a>Actualizaciones del sistema operativo

Al actualizar el sistema operativo a una nueva versión principal, primero debe desinstalar Defender para punto de conexión en Linux, instalar la actualización y, por último, volver a configurar Defender para punto de conexión en Linux en el dispositivo.

## <a name="references"></a>Referencias

- [Adición o eliminación de repositorios YUM](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Administración de paquetes con el administrador de paquetes dnf](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Adición y eliminación de repositorios APT](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Administración de apt-packages](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>Vea también
- [Investigar problemas de estado del agente](health-status.md)
