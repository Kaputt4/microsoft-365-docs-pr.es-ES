---
title: Crear un paquete
description: Cómo compilar el paquete
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 02/28/2022
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: Tinacyt
f1.keywords: NOCSH
ms.openlocfilehash: 277c185b633263a12687eec5a8eb9a1a34e1dbed
ms.sourcegitcommit: 23a90ed17cddf3b0db8d4084c8424f0fabd7b1de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2022
ms.locfileid: "62888157"
---
# <a name="build-a-package"></a>Crear un paquete
Un paquete es un .zip que contiene los scripts binarios y de prueba de la aplicación, que es el requisito previo para usar Test Base. Esta Guía de inicio rápido le guiará para crear el primer paquete, con el que puede realizar pruebas rápidas en la aplicación. 
  
*    *Una **prueba lista para su uso (OOB)** realiza una instalación, inicio, cierre y desinstalación de la aplicación. Después de la instalación, la rutina de inicio y cierre se repite 30 veces antes de ejecutar una sola desinstalación. La prueba de OOB proporciona telemetría estandarizada en el paquete para comparar entre Windows compilaciones.*  
    
Opcionalmente, puede descargar nuestro [paquete de ejemplo para](https://aka.ms/testbase-sample-package) hacer referencia y empezar por. 

## <a name="create-a-folder-structure"></a>Crear una estructura de carpetas 

En el equipo local, cree una estructura de carpetas de la siguiente manera:<br> 
![La estructura de carpetas usada para crear el paquete](Media/buildpackage1.png)

Estas carpetas se usan:
* **App\bin**: guarde los archivos binarios de aplicación y dependencia.<br> 
* **App\scripts**: guarde scripts para instalar, iniciar, cerrar y desinstalar la aplicación.<br> 
* **App\logs**: los scripts deben generar registros en esta carpeta y, a continuación, puede descargar y analizar registros una vez finalizada la prueba.<br> 

## <a name="copy-binary-files"></a>Copiar archivos binarios
Copie los archivos de instalación de la aplicación **en App\bin**. Si la aplicación tiene dependencias, debe instalarse primero. Además, copie los archivos de instalación de dependencia en **App\bin**.<br> 
![Ubicación de los archivos de aplicación en la carpeta](Media/buildpackage2.png)

## <a name="add-powershell-scripts"></a>Agregar scripts de PowerShell
Para realizar la prueba de OOB, deberá agregar scripts de PowerShell para instalar, iniciar, cerrar y desinstalar la aplicación.
> [!NOTE]  
> *En la prueba de OOB, se requieren scripts de instalación, inicio y cierre, mientras que el script de desinstalación es opcional*.
    
El script debe agregarse a la carpeta de la siguiente manera:  
![Ubicación de los archivos de scripts de powershell en la carpeta](Media/buildpackage3.png)

Un script suele incluir los siguientes comportamientos:<br> 
-   **Ejecute los comandos para instalar, iniciar, cerrar o desinstalar la aplicación**. Por ejemplo, si la aplicación es un archivo MSI, ejecute [msiexec](/windows-server/administration/windows-commands/msiexec) para instalarlo. <br> 
-   **Compruebe el resultado de la operación install/launch/close/uninstall**, devuelva el código de salida cero si se espera el resultado. Test Base marcará un script ejecutado como error si devuelve un código de salida distinto de cero.<br> 
-   **Guarde suficientes registros**, guarde los registros adecuados para su uso futuro.<br> 

Consulte los ejemplos siguientes. Simplemente puede copiarlos en los archivos y realizar los cambios correspondientes. <br>

**Ejemplo de script de instalación (App\scripts\install\job.ps1)**
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

**Ejemplo de script de inicio (App\scripts\launch\job.ps1)**
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

## <a name="compress-to-zip-file"></a>Comprimir a archivo zip
Después de preparar scripts y archivos binarios, procede a comprimir la carpeta en un archivo zip. Haz clic con el botón derecho en la carpeta Aplicación y **selecciona Comprimir a archivo ZIP**.<br>
![Comprimir a archivo zip](Media/buildpackage4.png)


## <a name="verify-your-package-locally-optional"></a>Comprobar el paquete localmente (opcional)
Después de compilar el paquete zip, puedes cargarlo en tu cuenta base de prueba. <br>
Sin embargo, es mejor ejecutar la prueba localmente para asegurarse de que los scripts funcionan correctamente antes de cargarlos. Una prueba local puede identificar rápidamente problemas y acelerar el proceso de carga. Para comprobar localmente, siga los pasos siguientes:<br>
1.  Preparar una máquina virtual (máquina virtual)<br>
    Se recomienda usar una máquina virtual para esta prueba local, ya que actualmente se necesita un entorno Windows limpia para cada prueba. Es fácil crear una máquina virtual de Windows en Azure ([inicio rápido Windows:](/azure/virtual-machines/windows/quick-create-portal) una máquina virtual), puede seleccionar una versión de Windows (imagen) adecuada para la prueba, por ejemplo, *Windows 10 Pro, versión 21H2.*<br>

2.  Copiar el paquete en la máquina virtual<br>
    Hay muchas maneras de copiar el archivo de paquete en la máquina virtual. Si usa una máquina virtual de Azure, puede elegir:
     -  Copie el archivo directamente en la conexión de Escritorio remoto. <br>
     -  Usar el recurso compartido de archivos de Azure ([Inicio rápido: Crear y administrar archivo de Azure](/azure/storage/files/storage-files-quick-create-use-windows))
    
    Puede crear una carpeta específica para esta prueba y copiar el archivo de paquete en esta carpeta. Por ejemplo, *C:\TestBase*.<br>
3.  Probar el paquete<br>
    Abra Windows PowerShell, cambie al directorio que contiene el paquete, por ejemplo, cd C:\TestBase y comience a ejecutar las pruebas en el paquete:<br>
    a.  Extraiga el archivo de paquete.
     -  *Expand-Archive -LiteralPath C:\TestBase\App.zip -DestinationPath C:\TestBase*<br>
    
    b.  Ejecute el script de instalación.  
     -  *C:\TestBase\App\scripts\install\job.ps1*<br>
    
    c.  Reinicie la máquina virtual si es necesario.<br>
    
    d.  Ejecute el script de inicio.
     -  *C:\TestBase\App\scripts\install\job.ps1*<br>
    
    e.  Ejecute el script close.
     -  *C:\TestBase\App\scripts\close\job.ps1*<br>
    
    f.  Ejecute el script de desinstalación (si tiene uno).
     -  *C:\TestBase\App\scripts\uninstall\job.ps1*<br>
    
    Después de cada paso, puede comprobar si hay algún problema en el script. Si todos los scripts se ejecutan como se esperaba, el paquete está listo para cargarse en la cuenta base de prueba.


## <a name="next-steps"></a>Pasos siguientes
[Upload un paquete](uploadApplication.md)
 
 
