---
title: Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que se incorpore a Microsoft Defender para el servicio de extremo.
keywords: configurar dispositivos de infraestructura de escritorio virtual (VDI), vdi, administración de dispositivos, configurar Microsoft Defender para endpoint, puntos de conexión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 555f96dc1f45fb6a406b5993d0b8e4a3745c283b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339639"
---
# <a name="onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Incorporación de los dispositivos de infraestructura de escritorio virtual (VDI) no persistentes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Dispositivos de infraestructura de escritorio virtual (VDI)
- Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente

Defender for Endpoint admite la incorporación de sesiones VDI no persistentes. 


Puede haber desafíos asociados al incorporar LOS VDIs. Los siguientes son los desafíos típicos de este escenario:

- Incorporación anticipada instantánea de sesiones de corta duración, que deben incorporarse a Defender for Endpoint antes del aprovisionamiento real.
- El nombre del dispositivo normalmente se reutiliza para nuevas sesiones.

Los dispositivos VDI pueden aparecer en el portal de Defender for Endpoint como:

- Entrada única para cada dispositivo.

  > [!NOTE]
  > En este caso, se debe configurar el *mismo* nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendido.

- Varias entradas para cada dispositivo: una para cada sesión.

Los siguientes pasos le guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.

>[!WARNING]
> En los entornos en los que hay configuraciones de recursos bajos, el procedimiento de arranque de VDI puede ralentizar la incorporación del sensor Defender for Endpoint. 


### <a name="for-windows-10-or-windows-server-2019"></a>Para Windows 10 o Windows Server 2019

1.  Abra el archivo de configuración .zip VDI (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del Asistente para incorporación de servicios. También puede obtener el paquete desde [Microsoft 365 Defender portal:](https://security.microsoft.com/)

    1. En el panel de navegación, **seleccione Configuración**  >  **Endpoints**  >  **Device management**  >  **Onboarding**.

    1. Seleccione Windows 10 como sistema operativo.

    1.  En el **campo Método de** implementación, seleccione Scripts de incorporación de VDI para puntos de conexión no **persistentes.**

    1. Haga **clic en Descargar paquete** y guarde el .zip archivo.

2. Copie los archivos de la carpeta WindowsDefenderATPOnboardingPackage extraída del archivo .zip en la imagen `golden/master` de la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

    1. Si no implementa una sola entrada para cada dispositivo, copie WindowsDefenderATPOnboardingScript.cmd.

    1. Si vas a implementar una sola entrada para cada dispositivo, copia tanto Onboard-NonPersistentMachine.ps1 como WindowsDefenderATPOnboardingScript.cmd.
    
    > [!NOTE]
    > Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, podría estar oculta. Tendrás que elegir la opción Mostrar **archivos y carpetas** ocultos en el Explorador de archivos.

3. Abra una ventana Editor de directivas de grupo local y vaya a **Configuración** del  >  **equipo Windows Configuración** inicio de  >    >  **scripts.**

   > [!NOTE]
   > La directiva de grupo de dominio también se puede usar para incorporar dispositivos VDI no persistentes.

4. Según el método que quiera implementar, siga los pasos correspondientes:

   - Para una sola entrada para cada dispositivo:
   
     Seleccione la **pestaña Scripts de PowerShell** y, a continuación, haga clic en Agregar **(el** Explorador de Windows se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente). Navegue a la incorporación del script de PowerShell `Onboard-NonPersistentMachine.ps1` . No es necesario especificar el otro archivo, ya que se desencadenará automáticamente.
   
   - Para varias entradas para cada dispositivo:
   
     Seleccione la **pestaña Scripts** y, a continuación, haga clic en Agregar **(Windows** Explorer se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente). Vaya al script bash de incorporación `WindowsDefenderATPOnboardingScript.cmd` .

5. Pruebe la solución:

   1. Crea un grupo de servidores con un dispositivo.
      
   1. Inicie sesión en el dispositivo.
      
   1. Cierre sesión desde el dispositivo.

   1. Inicie sesión en el dispositivo con otro usuario.
      
   1. Según el método que quiera implementar, siga los pasos correspondientes:
   
      - Para una sola entrada para cada dispositivo: 
    
        Compruebe solo una entrada en Microsoft 365 Defender portal.

      - Para varias entradas para cada dispositivo: 
       
        Compruebe varias entradas en Microsoft 365 Defender portal.

6. Haga **clic en Lista de** dispositivos en el panel de navegación.

7. Para usar la función de búsqueda, escriba el nombre del dispositivo y seleccione **Dispositivo** como tipo de búsqueda.


## <a name="for-downlevel-skus"></a>Para SKU de nivel inferior

> [!NOTE]
> El registro siguiente es relevante solo cuando el objetivo es lograr una "entrada única para cada dispositivo".

1. Establezca el valor del Registro en:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    o mediante la línea de comandos:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. Siga el [proceso de incorporación del servidor](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016). 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistente
Como práctica recomendada, se recomienda usar herramientas de mantenimiento sin conexión para aplicar revisiones a imágenes doradas o maestras.<br>
Por ejemplo, puede usar los siguientes comandos para instalar una actualización mientras la imagen permanece sin conexión:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obtener más información sobre los comandos DISM y el mantenimiento sin conexión, consulte los artículos siguientes:
- [Modificar una imagen Windows con DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opciones de administración de imágenes Command-Line DISM](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reducir el tamaño del almacén de componentes en una imagen Windows sin conexión](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Si el mantenimiento sin conexión no es una opción viable para el entorno VDI no persistente, se deben seguir los siguientes pasos para garantizar la coherencia y el estado del sensor:

1. Después de arrancar la imagen maestra para el mantenimiento o la revisión en línea, ejecute un script de offboarding para desactivar el sensor Defender for Endpoint. Para obtener más información, vea [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).

2. Asegúrese de que el sensor está detenido ejecutando el comando siguiente en una ventana cmd:

   ```console
   sc query sense
   ```

3. Servicio de la imagen según sea necesario.

4. Ejecute los siguientes comandos mediante PsExec.exe (que se pueden descargar para limpiar el contenido de la carpeta cibernética que el sensor puede haber acumulado https://download.sysinternals.com/files/PSTools.zip) desde el arranque:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Vuelva a sellar la imagen dorada/maestra como lo haría normalmente.

## <a name="related-topics"></a>Temas relacionados
- [Incorporación Windows 10 dispositivos con directiva de grupo](configure-endpoints-gp.md)
- [Incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](configure-endpoints-script.md)
- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](troubleshoot-onboarding.md)
