---
title: Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que se incorpore al servicio de prevención de pérdida de datos del punto de conexión de Microsoft 365.
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917956"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente

**Se aplica a:**
- [Prevención de pérdida de datos del extremo de Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)

- Dispositivos de infraestructura de escritorio virtual (VDI)

>[!WARNING]
> Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios. Actualmente, no se admiten escenarios de varias sesiones en Windows Virtual Desktop.

## <a name="onboard-vdi-devices"></a>Incorporar dispositivos VDI

La prevención de pérdida de datos del punto de conexión de Microsoft 365 admite la incorporación de sesiones VDI no persistentes. 

>[!Note]
>Para incorporar sesiones VDI no persistentes, los dispositivos VDI deben estar en Windows 10 1809 o versiones posteriores.

Puede haber desafíos asociados al incorporar LOS VDIs. Los siguientes son los desafíos típicos de este escenario:

- Incorporación anticipada instantánea de sesiones de corta duración, que deben incorporarse a la prevención de pérdida de datos del punto de conexión de Microsoft 365 antes del aprovisionamiento real.
- El nombre del dispositivo normalmente se reutiliza para nuevas sesiones.

Los dispositivos VDI pueden aparecer en el Centro de cumplimiento de Microsoft 365 como:

- Entrada única para cada dispositivo.  
Tenga en cuenta que, en este caso, *debe* configurarse el mismo nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendido.
- Varias entradas para cada dispositivo: una para cada sesión.

Los siguientes pasos le guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.

>[!WARNING]
> En entornos en los que hay configuraciones de recursos bajos, el procedimiento de arranque de VDI puede ralentizar la incorporación de prevención de pérdida de datos del punto de conexión de Microsoft 365. 

1.  Abra el archivo .zip del paquete de configuración VDI (*DeviceCompliancePackage.zip*) que descargó del Asistente para incorporación de servicios.

2.  En el panel de navegación, seleccione **Configuración**  >  **Incorporación de**  >  **dispositivos**.

3. En el **campo Método de** implementación, seleccione Scripts de incorporación de VDI para puntos de conexión no **persistentes.**

5. Haga **clic en Descargar paquete** y guarde el archivo .zip.

6. Copie los archivos de la carpeta DeviceCompliancePackage extraídos del archivo .zip en la `golden/master` imagen bajo la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

7. Si no implementa una sola entrada para cada dispositivo, copie DeviceComplianceOnboardingScript.cmd.

8. Si va a implementar una sola entrada para cada dispositivo, copie tanto Onboard-NonPersistentMachine.ps1 como DeviceComplianceOnboardingScript.cmd.
    
    > [!NOTE]
    > Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, podría estar oculta. Tendrás que elegir la opción Mostrar **archivos y carpetas** ocultos en el Explorador de archivos.

9. Abra una ventana del Editor de directivas de grupo local y vaya a **Configuración** del equipo Configuración de  >  **Windows**  >  **Scripts**  >  **Inicio**.

   > [!NOTE]
   > La directiva de grupo de dominio también se puede usar para incorporar dispositivos VDI no persistentes.

4. Según el método que quiera implementar, siga los pasos correspondientes:

   **Para una sola entrada para cada dispositivo**
   
   Seleccione la **pestaña Scripts de PowerShell** y, a continuación, haga clic en Agregar **(el** Explorador de Windows se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente). Navegue a la incorporación del script de PowerShell `Onboard-NonPersistentMachine.ps1` .
   
   **Para varias entradas para cada dispositivo:**
   
   Selecciona la **pestaña Scripts** y, a continuación, haz clic en **Agregar** (el Explorador de Windows se abrirá directamente en la ruta de acceso en la que has copiado el script de incorporación anteriormente). Vaya al script bash de incorporación `DeviceComplianceOnboardingScript.cmd` .

5. Pruebe la solución:

   1. Crea un grupo de servidores con un dispositivo.
      
   1. Inicie sesión en el dispositivo.
      
   1. Cierre sesión desde el dispositivo.

   1. Inicie sesión en el dispositivo con otro usuario.
      
   1. **Para una sola entrada para cada dispositivo:** compruebe solo una entrada en el Centro de seguridad de Microsoft Defender.<br>
      **Para varias entradas para cada dispositivo:** compruebe varias entradas en el Centro de seguridad de Microsoft Defender.

6. Haga **clic en Lista de** dispositivos en el panel de navegación.

7. Para usar la función de búsqueda, escriba el nombre del dispositivo y seleccione **Dispositivo** como tipo de búsqueda.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistente
Como práctica recomendada, se recomienda usar herramientas de mantenimiento sin conexión para aplicar revisiones a imágenes doradas o maestras.<br>
Por ejemplo, puede usar los siguientes comandos para instalar una actualización mientras la imagen permanece sin conexión:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obtener más información sobre los comandos DISM y el mantenimiento sin conexión, consulte los artículos siguientes:
- [Modificar una imagen de Windows con DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opciones de administración de imágenes Command-Line DISM](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reducir el tamaño del almacén de componentes en una imagen de Windows sin conexión](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Si el mantenimiento sin conexión no es una opción viable para el entorno VDI no persistente, se deben seguir los siguientes pasos para garantizar la coherencia y el estado del sensor:

1. Después de arrancar la imagen maestra para el mantenimiento en línea o la revisión, ejecute un script de offboarding para desactivar el sensor de prevención de pérdida de datos del extremo de Microsoft 365. Para obtener más información, vea [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).

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
- [Incorporación de dispositivos Windows 10 con la directiva de grupo](dlp-configure-endpoints-gp.md)
- [Incorporación de dispositivos Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](dlp-configure-endpoints-script.md)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)