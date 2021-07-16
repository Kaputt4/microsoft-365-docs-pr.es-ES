---
title: Implementar Microsoft Defender para Endpoint en Linux manualmente
ms.reviewer: ''
description: Describe cómo implementar Microsoft Defender para Endpoint en Linux manualmente desde la línea de comandos.
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
ms.openlocfilehash: 4c4ed845a31f044e17c97e0b43adfc86dd3f68ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454810"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a><span data-ttu-id="c2a9b-104">Implementar Microsoft Defender para Endpoint en Linux manualmente</span><span class="sxs-lookup"><span data-stu-id="c2a9b-104">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c2a9b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c2a9b-105">**Applies to:**</span></span>
- [<span data-ttu-id="c2a9b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c2a9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c2a9b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2a9b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c2a9b-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c2a9b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c2a9b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="c2a9b-110">En este artículo se describe cómo implementar Microsoft Defender para Endpoint en Linux manualmente.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-110">This article describes how to deploy Microsoft Defender for Endpoint on Linux manually.</span></span> <span data-ttu-id="c2a9b-111">Una implementación correcta requiere la finalización de todas las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="c2a9b-112">Implementar Microsoft Defender para Endpoint en Linux manualmente</span><span class="sxs-lookup"><span data-stu-id="c2a9b-112">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [<span data-ttu-id="c2a9b-113">Requisitos previos y requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="c2a9b-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="c2a9b-114">Configurar el repositorio de software de Linux</span><span class="sxs-lookup"><span data-stu-id="c2a9b-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="c2a9b-115">RHEL y variantes (CentOS y Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="c2a9b-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="c2a9b-116">SLES y variantes</span><span class="sxs-lookup"><span data-stu-id="c2a9b-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="c2a9b-117">Sistemas Ubuntu y Debian</span><span class="sxs-lookup"><span data-stu-id="c2a9b-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="c2a9b-118">Instalación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c2a9b-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="c2a9b-119">Descargar el paquete de incorporación</span><span class="sxs-lookup"><span data-stu-id="c2a9b-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="c2a9b-120">Configuración de cliente</span><span class="sxs-lookup"><span data-stu-id="c2a9b-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="c2a9b-121">Script del instalador</span><span class="sxs-lookup"><span data-stu-id="c2a9b-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="c2a9b-122">Problemas de instalación del registro</span><span class="sxs-lookup"><span data-stu-id="c2a9b-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="c2a9b-123">Actualizaciones del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="c2a9b-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="c2a9b-124">Desinstalación</span><span class="sxs-lookup"><span data-stu-id="c2a9b-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="c2a9b-125">Requisitos previos y requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="c2a9b-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="c2a9b-126">Antes de empezar, consulte [Microsoft Defender para Endpoint en Linux](microsoft-defender-endpoint-linux.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-126">Before you get started, see [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="c2a9b-127">Configurar el repositorio de software de Linux</span><span class="sxs-lookup"><span data-stu-id="c2a9b-127">Configure the Linux software repository</span></span>

<span data-ttu-id="c2a9b-128">Defender para Endpoint en Linux se puede implementar desde uno de los siguientes canales (que se indican a continuación como *[canal]):* *insiders-fast*, *insiders-slow* o *prod*. Cada uno de estos canales corresponde a un repositorio de software de Linux.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-128">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="c2a9b-129">A continuación se proporcionan instrucciones para configurar el dispositivo para que use uno de estos repositorios.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="c2a9b-130">La elección del canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="c2a9b-131">Los dispositivos *de insiders-fast* son los primeros en recibir actualizaciones y nuevas características, seguidos más adelante por *insiders-slow* y, por último, por *prod*.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="c2a9b-132">Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa para que usen *insiders-fast* o *insiders-slow*.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="c2a9b-133">Cambiar el canal después de la instalación inicial requiere que se vuelva a instalar el producto.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="c2a9b-134">Para cambiar el canal de producto: desinstale el paquete existente, vuelva a configurar el dispositivo para que use el nuevo canal y siga los pasos descritos en este documento para instalar el paquete desde la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="c2a9b-135">RHEL y variantes (CentOS y Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="c2a9b-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="c2a9b-136">Instale `yum-utils` si aún no está instalado:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="c2a9b-137">Tenga en cuenta la distribución y la versión e identifique la entrada más cercana (por mayor y, a continuación, secundaria) para ella en `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="c2a9b-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="c2a9b-138">Por ejemplo, RHEL 7.9 está más cerca de 7,4 que de 8.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="c2a9b-139">En los comandos siguientes, reemplace *[distro]* y *[version]* por la información que haya identificado:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2a9b-140">En el caso de Oracle Linux, reemplace *[distro]* por "rhel".</span><span class="sxs-lookup"><span data-stu-id="c2a9b-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="c2a9b-141">Por ejemplo, si ejecuta CentOS 7 y desea implementar Defender para Endpoint en Linux desde el *canal prod:*</span><span class="sxs-lookup"><span data-stu-id="c2a9b-141">For example, if you are running CentOS 7 and want to deploy Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="c2a9b-142">O bien, si quieres explorar nuevas características en dispositivos seleccionados, es posible que quieras implementar Microsoft Defender para Endpoint en Linux en el canal *insiders-fast:*</span><span class="sxs-lookup"><span data-stu-id="c2a9b-142">Or if you wish to explore new features on selected devices, you might want to deploy Microsoft Defender for Endpoint on Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="c2a9b-143">Instalar la clave pública gpg de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="c2a9b-144">Descargue y haga que se usen todos los metadatos de los repositorios de yum habilitados actualmente:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="c2a9b-145">SLES y variantes</span><span class="sxs-lookup"><span data-stu-id="c2a9b-145">SLES and variants</span></span>

- <span data-ttu-id="c2a9b-146">Tenga en cuenta la distribución y la versión e identifique la entrada más cercana (por mayor y, a continuación, secundaria) para ella en `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="c2a9b-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="c2a9b-147">En los siguientes comandos, reemplace *[distro]* y *[version]* por la información que haya identificado:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="c2a9b-148">Por ejemplo, si ejecuta SLES 12 y desea implementar Microsoft Defender para Endpoint en Linux desde el *canal prod:*</span><span class="sxs-lookup"><span data-stu-id="c2a9b-148">For example, if you are running SLES 12 and wish to deploy Microsoft Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="c2a9b-149">Instalar la clave pública gpg de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="c2a9b-150">Sistemas Ubuntu y Debian</span><span class="sxs-lookup"><span data-stu-id="c2a9b-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="c2a9b-151">Instale `curl` si aún no está instalado:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="c2a9b-152">Instale `libplist-utils` si aún no está instalado:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="c2a9b-153">Tenga en cuenta la distribución y la versión e identifique la entrada más cercana (por mayor y, a continuación, secundaria) para ella en `https://packages.microsoft.com/config` .</span><span class="sxs-lookup"><span data-stu-id="c2a9b-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="c2a9b-154">En el comando siguiente, reemplace *[distro]* y *[versión]* por la información que haya identificado:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="c2a9b-155">Por ejemplo, si está ejecutando Ubuntu 18.04 y desea implementar MDE para Linux desde el *canal prod:*</span><span class="sxs-lookup"><span data-stu-id="c2a9b-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="c2a9b-156">Instale la configuración del repositorio:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="c2a9b-157">Por ejemplo, si ha elegido *canal prod:*</span><span class="sxs-lookup"><span data-stu-id="c2a9b-157">For example, if you chose *prod* channel:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- <span data-ttu-id="c2a9b-158">Instale el `gpg` paquete si aún no está instalado:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="c2a9b-159">Si `gpg` no está disponible, instale `gnupg` .</span><span class="sxs-lookup"><span data-stu-id="c2a9b-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="c2a9b-160">Instalar la clave pública gpg de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="c2a9b-161">Instale el controlador https si aún no está presente:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="c2a9b-162">Actualice los metadatos del repositorio:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="c2a9b-163">Instalación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c2a9b-163">Application installation</span></span>

- <span data-ttu-id="c2a9b-164">RHEL y variantes (CentOS y Oracle Linux):</span><span class="sxs-lookup"><span data-stu-id="c2a9b-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="c2a9b-165">Si tienes varios repositorios de Microsoft configurados en el dispositivo, puedes ser específico sobre el repositorio desde el que instalar el paquete.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="c2a9b-166">En el ejemplo siguiente se muestra cómo instalar el paquete desde el canal si también tienes configurado el canal `production` de repositorio en este `insiders-fast` dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="c2a9b-167">Esta situación puede ocurrir si usas varios productos de Microsoft en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="c2a9b-168">Según la distribución y la versión del servidor, el alias de repositorio puede ser diferente al del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

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

- <span data-ttu-id="c2a9b-169">SLES y variantes:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="c2a9b-170">Si tienes varios repositorios de Microsoft configurados en el dispositivo, puedes ser específico sobre el repositorio desde el que instalar el paquete.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="c2a9b-171">En el ejemplo siguiente se muestra cómo instalar el paquete desde el canal si también tienes configurado el canal `production` de repositorio en este `insiders-fast` dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="c2a9b-172">Esta situación puede ocurrir si usas varios productos de Microsoft en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

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

- <span data-ttu-id="c2a9b-173">Sistema Ubuntu y Debian:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="c2a9b-174">Si tienes varios repositorios de Microsoft configurados en el dispositivo, puedes ser específico sobre el repositorio desde el que instalar el paquete.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="c2a9b-175">En el ejemplo siguiente se muestra cómo instalar el paquete desde el canal si también tienes configurado el canal `production` de repositorio en este `insiders-fast` dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="c2a9b-176">Esta situación puede ocurrir si usas varios productos de Microsoft en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="c2a9b-177">Descargar el paquete de incorporación</span><span class="sxs-lookup"><span data-stu-id="c2a9b-177">Download the onboarding package</span></span>

<span data-ttu-id="c2a9b-178">Descargue el paquete de incorporación desde Microsoft 365 Defender portal:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-178">Download the onboarding package from Microsoft 365 Defender portal:</span></span>

1. <span data-ttu-id="c2a9b-179">En el portal Microsoft 365 Defender, vaya **a Configuración > Endpoints > Administración** de dispositivos > Incorporación .</span><span class="sxs-lookup"><span data-stu-id="c2a9b-179">In the Microsoft 365 Defender portal, go to **Settings > Endpoints > Device management > Onboarding**.</span></span>
2. <span data-ttu-id="c2a9b-180">En el primer menú desplegable, seleccione **Linux Server** como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="c2a9b-181">En el segundo menú desplegable, seleccione **Script local** como método de implementación.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-181">In the second drop-down menu, select **Local Script** as the deployment method.</span></span>
3. <span data-ttu-id="c2a9b-182">Seleccione **Descargar paquete de incorporación**.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="c2a9b-183">Guarde el archivo como WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft 365 Defender captura de pantalla del portal](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="c2a9b-185">Desde un símbolo del sistema, compruebe que tiene el archivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="c2a9b-186">Extraiga el contenido del archivo:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-186">Extract the contents of the archive:</span></span>

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


## <a name="client-configuration"></a><span data-ttu-id="c2a9b-187">Configuración de clientes</span><span class="sxs-lookup"><span data-stu-id="c2a9b-187">Client configuration</span></span>

1. <span data-ttu-id="c2a9b-188">Copia MicrosoftDefenderATPOnboardingLinuxServer.py en el dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="c2a9b-189">Inicialmente, el dispositivo cliente no está asociado a una organización.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="c2a9b-190">Tenga en cuenta que *el atributo orgId* está en blanco:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="c2a9b-191">Ejecute MicrosoftDefenderATPOnboardingLinuxServer.py.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py.</span></span> 
   
    >[!NOTE]
    ><span data-ttu-id="c2a9b-192">Para ejecutar este comando, debes haber `python` instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-192">To run this command, you must have `python` installed on the device.</span></span> <span data-ttu-id="c2a9b-193">Si estás ejecutando RHEL 8.x o Ubuntu 20.04 o posterior, deberás usar Python 3 en lugar de Python.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-193">If you're running RHEL 8.x or Ubuntu 20.04 or higher, then you will need to use Python 3 instead of Python.</span></span>



    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="c2a9b-194">Compruebe que el dispositivo esté asociado a su organización e informe de un identificador de organización válido:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-194">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="c2a9b-195">Unos minutos después de completar la instalación, puede ver el estado ejecutando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-195">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="c2a9b-196">Un valor devuelto `1` de indica que el producto funciona como se esperaba:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-196">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="c2a9b-197">Cuando el producto se inicia por primera vez, descarga las definiciones de antimalware más recientes.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-197">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="c2a9b-198">Según la conexión a Internet, esto puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-198">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="c2a9b-199">Durante este tiempo, el comando anterior devuelve un valor de `false` .</span><span class="sxs-lookup"><span data-stu-id="c2a9b-199">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="c2a9b-200">Puede comprobar el estado de la actualización de definiciones con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-200">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="c2a9b-201">Tenga en cuenta que es posible que también necesite configurar un proxy después de completar la instalación inicial.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-201">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="c2a9b-202">Consulte [Configure Defender for Endpoint on Linux para la detección de proxy estático: configuración posterior a la instalación.](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)</span><span class="sxs-lookup"><span data-stu-id="c2a9b-202">See [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="c2a9b-203">Ejecute una prueba de detección para comprobar que el dispositivo está correctamente incorporado e informando al servicio.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-203">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="c2a9b-204">Realice los pasos siguientes en el dispositivo recién incorporado:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-204">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="c2a9b-205">Asegúrese de que la protección en tiempo real está habilitada (se indica mediante el resultado de `1` la ejecución del siguiente comando):</span><span class="sxs-lookup"><span data-stu-id="c2a9b-205">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="c2a9b-206">Abra una ventana terminal.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-206">Open a Terminal window.</span></span> <span data-ttu-id="c2a9b-207">Copie y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-207">Copy and execute the following command:</span></span>

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="c2a9b-208">Defender for Endpoint en Linux debería haber puesto el archivo en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-208">The file should have been quarantined by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="c2a9b-209">Use el siguiente comando para enumerar todas las amenazas detectadas:</span><span class="sxs-lookup"><span data-stu-id="c2a9b-209">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="experience-linux-endpoint-detection-and-response-edr-capabilities-with-simulated-attacks"></a><span data-ttu-id="c2a9b-210">Experiencia de detección y respuesta de puntos de conexión Linux (EDR) con ataques simulados</span><span class="sxs-lookup"><span data-stu-id="c2a9b-210">Experience Linux endpoint detection and response (EDR) capabilities with simulated attacks</span></span>

<span data-ttu-id="c2a9b-211">Para probar las funcionalidades de EDR para Linux, siga los pasos siguientes para simular una detección en el servidor Linux e investigar el caso.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-211">To test out the functionalities of EDR for Linux, follow the steps below to simulate a detection on your Linux server and investigate the case.</span></span> 

1.  <span data-ttu-id="c2a9b-212">Compruebe que el servidor Linux incorporado aparezca en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-212">Verify that the onboarded Linux server appears in Microsoft 365 Defender.</span></span> <span data-ttu-id="c2a9b-213">Si se trata de la primera incorporación de la máquina, puede tardar hasta 20 minutos hasta que aparezca.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-213">If this is the first onboarding of the machine, it can take up to 20 minutes until it appears.</span></span> 

2.  <span data-ttu-id="c2a9b-214">Descargue y extraiga el [archivo de script](https://aka.ms/LinuxDIY) en un servidor Linux incorporado y ejecute el siguiente comando: `./mde_linux_edr_diy.sh`</span><span class="sxs-lookup"><span data-stu-id="c2a9b-214">Download and extract the [script file](https://aka.ms/LinuxDIY) to an onboarded Linux server and run the following command: `./mde_linux_edr_diy.sh`</span></span>

3.  <span data-ttu-id="c2a9b-215">Después de unos minutos, se debe generar una detección en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-215">After a few minutes, a detection should be raised in Microsoft 365 Defender.</span></span>

4.  <span data-ttu-id="c2a9b-216">Vea los detalles de la alerta, la escala de tiempo de la máquina y realice los pasos de investigación típicos.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-216">Look at the alert details, machine timeline, and perform your typical investigation steps.</span></span>




## <a name="installer-script"></a><span data-ttu-id="c2a9b-217">Script del instalador</span><span class="sxs-lookup"><span data-stu-id="c2a9b-217">Installer script</span></span>

<span data-ttu-id="c2a9b-218">Como alternativa, puede usar un script bash del [instalador](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) automatizado proporcionado en nuestro [repositorio GitHub público](https://github.com/microsoft/mdatp-xplat/).</span><span class="sxs-lookup"><span data-stu-id="c2a9b-218">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="c2a9b-219">El script identifica la distribución y la versión y configura el dispositivo para extraer el paquete más reciente e instalarlo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-219">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="c2a9b-220">También puede incorporar un script proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-220">You can also onboard with a provided script.</span></span>

```bash
❯ ./mde_installer.sh --help
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

<span data-ttu-id="c2a9b-221">Lea más [aquí](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span><span class="sxs-lookup"><span data-stu-id="c2a9b-221">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="c2a9b-222">Problemas de instalación del registro</span><span class="sxs-lookup"><span data-stu-id="c2a9b-222">Log installation issues</span></span>

<span data-ttu-id="c2a9b-223">Consulte [Problemas de instalación del registro](linux-resources.md#log-installation-issues) para obtener más información sobre cómo encontrar el registro generado automáticamente que crea el instalador cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-223">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="c2a9b-224">Actualizaciones del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="c2a9b-224">Operating system upgrades</span></span>

<span data-ttu-id="c2a9b-225">Al actualizar el sistema operativo a una nueva versión principal, primero debes desinstalar Defender para Endpoint en Linux, instalar la actualización y, por último, volver a configurar Defender para Endpoint en Linux en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-225">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a><span data-ttu-id="c2a9b-226">Cómo migrar de Insiders-Fast al canal de producción</span><span class="sxs-lookup"><span data-stu-id="c2a9b-226">How to migrate from Insiders-Fast to Production channel</span></span>

1. <span data-ttu-id="c2a9b-227">Desinstale la versión "Insiders-Fast channel" de Defender para Endpoint en Linux.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-227">Uninstall the “Insiders-Fast channel” version of Defender for Endpoint on Linux.</span></span>

    ``
    sudo yum remove mdatp
    ``

1. <span data-ttu-id="c2a9b-228">Deshabilitar el repositorio de defender para endpoint en Linux Insiders-Fast linux  ``
    sudo yum repolist
    ``</span><span class="sxs-lookup"><span data-stu-id="c2a9b-228">Disable the Defender for Endpoint on Linux Insiders-Fast repo  ``
    sudo yum repolist
 ``</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2a9b-229">La salida debe mostrar "packages-microsoft-com-fast-prod".</span><span class="sxs-lookup"><span data-stu-id="c2a9b-229">The output should show “packages-microsoft-com-fast-prod”.</span></span>

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. <span data-ttu-id="c2a9b-230">Vuelva a implementar MDE para Linux mediante el "Canal de producción".</span><span class="sxs-lookup"><span data-stu-id="c2a9b-230">Redeploy MDE for Linux using the “Production channel”.</span></span>


## <a name="uninstallation"></a><span data-ttu-id="c2a9b-231">Desinstalación</span><span class="sxs-lookup"><span data-stu-id="c2a9b-231">Uninstallation</span></span>

<span data-ttu-id="c2a9b-232">Consulta [Desinstalar para](linux-resources.md#uninstall) obtener más información sobre cómo quitar Defender for Endpoint en Linux de los dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="c2a9b-232">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint on Linux from client devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2a9b-233">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c2a9b-233">See also</span></span>
- [<span data-ttu-id="c2a9b-234">Investigar problemas de estado del agente</span><span class="sxs-lookup"><span data-stu-id="c2a9b-234">Investigate agent health issues</span></span>](health-status.md)
