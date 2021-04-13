---
title: Solucionar problemas de instalación de ATP de Microsoft Defender para Linux
ms.reviewer: ''
description: Solucionar problemas de instalación de ATP de Microsoft Defender para Linux
keywords: microsoft, defender, atp, linux, instalación
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
ms.openlocfilehash: 347528def6929dde200249cd9710f7ce33484c7f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688818"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="9b7a4-104">Solucionar problemas de instalación de Microsoft Defender para Endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="9b7a4-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9b7a4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9b7a4-105">**Applies to:**</span></span>
- [<span data-ttu-id="9b7a4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9b7a4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9b7a4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b7a4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9b7a4-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9b7a4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9b7a4-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="9b7a4-110">Comprobar si la instalación se ha instalado correctamente</span><span class="sxs-lookup"><span data-stu-id="9b7a4-110">Verify if installation succeeded</span></span>

<span data-ttu-id="9b7a4-111">Un error en la instalación puede o no provocar un mensaje de error significativo por parte del administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="9b7a4-112">Para comprobar si la instalación se ha hecho correctamente, obtenga y compruebe los registros de instalación mediante:</span><span class="sxs-lookup"><span data-stu-id="9b7a4-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

<span data-ttu-id="9b7a4-113">Un resultado del comando anterior con la fecha y hora correctas de instalación indica que se ha correcto.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="9b7a4-114">Compruebe también la [configuración del cliente](linux-install-manually.md#client-configuration) para comprobar el estado del producto y detectar el archivo de texto EICAR.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="9b7a4-115">Asegúrese de que tiene el paquete correcto</span><span class="sxs-lookup"><span data-stu-id="9b7a4-115">Make sure you have the correct package</span></span>

<span data-ttu-id="9b7a4-116">Tenga en cuenta que el paquete que va a instalar coincide con la distribución y la versión del host.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="9b7a4-117">paquete</span><span class="sxs-lookup"><span data-stu-id="9b7a4-117">package</span></span>                       | <span data-ttu-id="9b7a4-118">distribución</span><span class="sxs-lookup"><span data-stu-id="9b7a4-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="9b7a4-119">mdatp-rhel8. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="9b7a4-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="9b7a4-120">Oracle, RHEL y CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="9b7a4-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="9b7a4-121">mdatp-sles12. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="9b7a4-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="9b7a4-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="9b7a4-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="9b7a4-123">mdatp-sles15. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="9b7a4-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="9b7a4-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="9b7a4-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="9b7a4-125">mdatp. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="9b7a4-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="9b7a4-126">Oracle, RHEL y CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="9b7a4-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="9b7a4-127">mdatp. Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="9b7a4-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="9b7a4-128">Debian y Ubuntu 16.04, 18.04 y 20.04</span><span class="sxs-lookup"><span data-stu-id="9b7a4-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="9b7a4-129">Para [la implementación manual,](linux-install-manually.md)asegúrese de que se han elegido el distro y la versión correctas.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="9b7a4-130">Error en la instalación</span><span class="sxs-lookup"><span data-stu-id="9b7a4-130">Installation failed</span></span>

<span data-ttu-id="9b7a4-131">Compruebe si el servicio mdatp se está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="9b7a4-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="9b7a4-132">Pasos para solucionar problemas si el servicio mdatp no se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="9b7a4-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="9b7a4-133">Compruebe si existe el usuario "mdatp":</span><span class="sxs-lookup"><span data-stu-id="9b7a4-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="9b7a4-134">Si no hay salida, ejecute</span><span class="sxs-lookup"><span data-stu-id="9b7a4-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="9b7a4-135">Intente habilitar y reiniciar el servicio con:</span><span class="sxs-lookup"><span data-stu-id="9b7a4-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="9b7a4-136">Si no se encuentra mdatp.service al ejecutar el comando anterior, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9b7a4-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="9b7a4-137">donde ```<systemd_path>``` está para las distribuciones de Ubuntu y Debian y para ```/lib/systemd/system``` ```/usr/lib/systemd/system``` Rhel, CentOS, Oracle y SLES.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-137">where ```<systemd_path>``` is ```/lib/systemd/system``` for Ubuntu and Debian distributions and ```/usr/lib/systemd/system``` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="9b7a4-138">A continuación, vuelva a ejecutar el paso 2.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="9b7a4-139">Si los pasos anteriores no funcionan, compruebe si SELinux está instalado y en modo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="9b7a4-140">Si es así, intenta establecerlo en modo permisivo (preferiblemente) o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="9b7a4-141">Se puede hacer estableciendo el parámetro en "permisivo" o "deshabilitado" en el archivo, seguido `SELINUX` `/etc/selinux/config` del reinicio.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="9b7a4-142">Consulta la página man de selinux para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="9b7a4-143">Ahora intente reiniciar el servicio mdatp mediante el paso 2.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="9b7a4-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="9b7a4-145">Si `/opt` el directorio es un vínculo simbólico, cree un montaje de enlace para `/opt/microsoft` .</span><span class="sxs-lookup"><span data-stu-id="9b7a4-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="9b7a4-146">Asegúrese de que el demonio tiene permiso ejecutable.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="9b7a4-147">Si el demonio no tiene permisos ejecutables, haga que sea ejecutable mediante:</span><span class="sxs-lookup"><span data-stu-id="9b7a4-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="9b7a4-148">y vuelva a intentar ejecutar el paso 2.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-148">and retry running step 2.</span></span>

7. <span data-ttu-id="9b7a4-149">Asegúrese de que el sistema de archivos que contiene wdavdaemon no esté montado con "noexec".</span><span class="sxs-lookup"><span data-stu-id="9b7a4-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="9b7a4-150">Si se está ejecutando el servicio mdatp, pero la detección de archivos de texto EICAR no funciona</span><span class="sxs-lookup"><span data-stu-id="9b7a4-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="9b7a4-151">Compruebe el tipo de sistema de archivos mediante:</span><span class="sxs-lookup"><span data-stu-id="9b7a4-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="9b7a4-152">Los sistemas de archivos compatibles actualmente para la actividad en tiempo de acceso se enumeran [aquí.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="9b7a4-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="9b7a4-153">Los archivos fuera de estos sistemas de archivos no se examinarán.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="9b7a4-154">La herramienta de línea de comandos "mdatp" no funciona</span><span class="sxs-lookup"><span data-stu-id="9b7a4-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="9b7a4-155">Si al ejecutar la herramienta de línea de `mdatp` comandos se produce un `command not found` error, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9b7a4-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="9b7a4-156">e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-156">and try again.</span></span>

    <span data-ttu-id="9b7a4-157">Si ninguno de los pasos anteriores ayuda, recopile los registros de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="9b7a4-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="9b7a4-158">La ruta de acceso a un archivo zip que contiene los registros se mostrará como salida.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="9b7a4-159">Llegue a nuestro servicio de atención al cliente con estos registros.</span><span class="sxs-lookup"><span data-stu-id="9b7a4-159">Reach out to our customer support with these logs.</span></span>
