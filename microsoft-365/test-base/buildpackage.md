---
title: Compilación de un paquete
description: Cómo compilar el paquete
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 02/28/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: Tinacyt
f1.keywords: NOCSH
ms.openlocfilehash: 75de203a09b27870287ec1253d2f485575d188ee
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315534"
---
# <a name="build-a-package"></a>Compilación de un paquete

Un paquete es un archivo .zip que contiene los scripts binarios y de prueba de la aplicación, que es el requisito previo para usar Test Base. Este inicio rápido le guiará para compilar el primer paquete, con el que puede realizar pruebas rápidas en la aplicación.

- *Una prueba lista para usar **(OOB)** realiza una instalación, inicio, cierre y desinstalación de la aplicación. Después de la instalación, la rutina de inicio y cierre se repite 30 veces antes de que se ejecute una sola desinstalación. La prueba de OOB proporciona telemetría estandarizada en el paquete para compararlo entre compilaciones de Windows.*

Opcionalmente, puede descargar nuestro [paquete de ejemplo](https://aka.ms/testbase-sample-package) para hacer referencia y empezar por.

## <a name="create-a-folder-structure"></a>Creación de una estructura de carpetas

En el equipo local, cree una estructura de carpetas como se indica a continuación:

![La estructura de carpetas usada para crear el paquete](Media/buildpackage1.png)

Estas carpetas se usan:

- **App\bin**: guarde los archivos binarios de aplicación y dependencia.
- **App\scripts**: guarde los scripts para instalar, iniciar, cerrar y desinstalar la aplicación.
- **App\logs**: los scripts deben generar registros en esta carpeta y, a continuación, puede descargar y analizar los registros una vez finalizada la prueba.

## <a name="copy-binary-files"></a>Copiar archivos binarios

Copie los archivos de instalación de la aplicación en **App\bin**. Si la aplicación tiene dependencias, primero deben instalarse. Además, copie los archivos de instalación de dependencias en **App\bin**.

![Ubicación de los archivos de aplicación en la carpeta](Media/buildpackage2.png)

## <a name="add-powershell-scripts"></a>Adición de scripts de PowerShell

Para realizar la prueba de OOB, deberá agregar scripts de PowerShell para instalar, iniciar, cerrar y desinstalar la aplicación.

> [!NOTE]
> *En OOB, se requieren scripts de prueba, instalación, inicio y cierre, mientras que el script de desinstalación es opcional*.

El script debe agregarse a la carpeta de la siguiente manera:

![Ubicación de los archivos de scripts de PowerShell en la carpeta](Media/buildpackage3.png)

Normalmente, un script incluye los siguientes comportamientos:

- **Ejecute los comandos para instalar, iniciar, cerrar o desinstalar la aplicación**. Por ejemplo, si la aplicación es un archivo MSI, ejecute [msiexec](/windows-server/administration/windows-commands/msiexec) para instalarlo.
- **Compruebe el resultado de la operación de instalación, inicio, cierre o desinstalación** y devuelva código de salida cero si se espera el resultado. Test Base marcará una ejecución de script como un error si devuelve un código de salida distinto de cero.
- **Guarde suficientes registros**, guarde los registros adecuados para su uso futuro.

Consulte los ejemplos siguientes. Simplemente puede copiarlos en sus archivos y realizar cambios en consecuencia.

**Ejemplo de script de instalación (App\scripts\install\job.ps1)**:

```powershell
        push-location $PSScriptRoot
        $exit_code = 0
        $script_name = $myinvocation.mycommand.name
        $log_dir = "$PSScriptRoot\..\..\logs"
        $log_file = "$log_dir\$script_name.log"

        if(-not (test-path -path $log_dir )) {
            new-item -itemtype directory -path $log_dir
        }

        Function log {
           Param ([string]$log_string)
           write-host $log_string
           add-content $log_file -value $log_string
        }

        log("Installing TestBaseM365 Digital Clock")
        push-location "..\..\bin"
        if ([Environment]::Is64BitProcess) {
            $installer_name = "TestBaseM365DigitalClock.msi"
        }
        else {
            $installer_name = "TestBaseM365DigitalClock.msi"
        }
        $arguments = "/i "+$installer_name+" /quiet /L*v "+"$log_dir"+"\atp-client-installation.log"

        $installer = Start-Process msiexec.exe $arguments -wait -passthru
        pop-location

        if ($installer.exitcode -eq 0) {
            log("Installation succesful as $($installer.exitcode)")
        }
        else {
            log("Error: Installation failed as $($installer.exitcode)")
            $exit_code = $installer.exitcode
        }

        log("Installation script finished as $exit_code")
        pop-location
        exit $exit_code
```

**Ejemplo de script de inicio (App\scripts\launch\job.ps1)**:

```powershell
        push-location $PSScriptRoot
        $exit_code = 0
        $script_name = $myinvocation.mycommand.name
        $log_dir = "$PSScriptRoot\..\..\logs"
        $log_file = "$log_dir\$script_name.log"

        if(-not (test-path -path $log_dir )) {
            new-item -itemtype directory -path $log_dir
        }

        Function log {
           Param ([string]$log_string)
           write-host $log_string
           add-content $log_file -value $log_string
        }

        log("Launch TestBaseM365 Digital Clock")

        $PROCESS_NAME = "DigitalClock"
        $exePath = "C:\Program Files\Test Base M365\DigitalClock\DigitalClock.exe"

        Start-Process -FilePath $exePath

         if (Get-Process -Name $PROCESS_NAME) {
                log("Launch successfully $PROCESS_NAME...")
                $exit_code = 0
         }
         else {
            log("Not launched $PROCESS_NAME...")
            $exit_code = 1
         }

        log("Launch script finished as $exit_code")
        pop-location
        exit $exit_code
```

## <a name="compress-to-zip-file"></a>Comprimir en un archivo zip

Una vez preparados los scripts y los archivos binarios, se comprime la carpeta en un archivo ZIP. Haga clic con el botón derecho en la carpeta Aplicación y seleccione **Comprimir en archivo ZIP**.

![Comprimir en un archivo zip](Media/buildpackage4.png)

## <a name="verify-your-package-locally-optional"></a>Comprobar el paquete localmente (opcional)

Después de compilar el paquete zip, puede cargarlo en la cuenta de Test Base.

Sin embargo, se recomienda ejecutar la prueba localmente para asegurarse de que los scripts funcionan correctamente antes de cargarlos. Una prueba local puede identificar rápidamente los problemas y acelerar el proceso de carga. Para comprobar localmente, siga estos pasos:

1. Preparación de una máquina virtual (máquina virtual)

   Se recomienda usar una máquina virtual para esta prueba local, ya que actualmente se necesita un entorno de Windows limpio para cada prueba. Es fácil crear una máquina virtual Windows en Azure ([inicio rápido: Máquina virtual Windows](/azure/virtual-machines/windows/quick-create-portal)), puede seleccionar una versión adecuada de Windows (imagen) para la prueba, por ejemplo, *Windows 10 Pro, versión 21H2.*<br>

2. Copia del paquete en la máquina virtual

   Hay muchas maneras de copiar el archivo de paquete en la máquina virtual. Si usa una máquina virtual de Azure, puede elegir:

     - Copie el archivo directamente en la conexión a Escritorio remoto.
     - Uso del recurso compartido de archivos de Azure ([inicio rápido: Creación y administración de archivos de Azure](/azure/storage/files/storage-files-quick-create-use-windows))

   Puede crear una carpeta específica para esta prueba y copiar el archivo de paquete en esta carpeta. Por ejemplo, *C:\TestBase*.

3. Prueba del paquete

   Abra Windows PowerShell, cambie al directorio que contiene el paquete, por ejemplo, `cd C:\TestBase`y empiece a ejecutar las pruebas en el paquete:

   1. Extraiga el archivo del paquete.

      ```powershell
      Expand-Archive -LiteralPath C:\TestBase\App.zip -DestinationPath C:\TestBase
      ```

   2. Ejecute el script de instalación.

      ```powershell
      C:\TestBase\App\scripts\install\job.ps1
      ```

   3. Reinicie la máquina virtual si es necesario.

   4. Ejecute el script de inicio.

      ```powershell
      C:\TestBase\App\scripts\install\job.ps1
      ```

   5. Ejecute el script de cierre.

      ```powershell
      C:\TestBase\App\scripts\close\job.ps1
      ```

   6. Ejecute el script de desinstalación (si tiene uno).

      ```powershell
      C:\TestBase\App\scripts\uninstall\job.ps1
      ```

Después de cada paso, puede comprobar si hay algún problema en el script. Si todos los scripts se ejecutan según lo esperado, el paquete está listo para cargarse en la cuenta base de prueba.

## <a name="next-steps"></a>Siguientes pasos

[Carga de un paquete](uploadApplication.md)
