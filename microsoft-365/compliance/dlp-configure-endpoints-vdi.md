---
title: Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados
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
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que estén integrados en el servicio de prevención de pérdida de datos de extremos de Microsoft 365.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769511"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados

**Se aplica a:**
- [Prevención de pérdida de datos (DLP) de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)

- Dispositivos de infraestructura de escritorio virtual (VDI)

>[!WARNING]
> La compatibilidad de prevención de pérdida de datos de extremos de Microsoft 365 para el escritorio virtual de Windows admite escenarios de sesión única. Actualmente no se admiten escenarios de sesiones múltiples en el escritorio virtual de Windows.

## <a name="onboard-vdi-devices"></a>Dispositivos VDI incorporados

La prevención de pérdida de datos de Microsoft 365 Endpoint admite la incorporación de sesiones de VDI no persistentes. 

>[!Note]
>Para incorporar sesiones de VDI no persistentes, los dispositivos de VDI deben estar en Windows 10 1809 o versiones posteriores.

Es posible que se produzcan retos asociados al VDIs de la incorporación. Los siguientes son desafíos típicos para este escenario:

- Incorporación rápida instantánea de sesiones de corta duración, que deben incorporarse a la prevención de pérdida de datos de Microsoft 365 Endpoint antes del aprovisionamiento real.
- El nombre del dispositivo suele reutilizarse para las sesiones nuevas.

Los dispositivos de VDI pueden aparecer en el centro de cumplimiento de Microsoft 365 como:

- Entrada única para cada dispositivo.  
Tenga en cuenta que, en este caso, el *mismo* nombre de dispositivo debe configurarse cuando se crea la sesión (por ejemplo, mediante un archivo de respuesta de instalación desatendida).
- Varias entradas para cada dispositivo: uno para cada sesión.

Los siguientes pasos le guiarán por los dispositivos VDI de incorporación y resaltarán los pasos para las entradas únicas y múltiples.

>[!WARNING]
> Para los entornos en los que hay configuraciones de recursos insuficientes, el procedimiento de arranque de VDI podría ralentizar la incorporación de prevención de pérdida de datos de extremos de Microsoft 365. 

1.  Abra el archivo. zip del paquete de configuración de VDI ( *DeviceCompliancePackage.zip* ) que ha descargado desde el Asistente de incorporación de servicios.

2.  En el panel de navegación, seleccione la incorporación de la incorporación de dispositivos de **configuración**  >  **Device onboarding**  >  **Onboarding** .

3. En el campo **método de implementación** , seleccione **scripts de incorporación de VDI para los extremos no persistentes** .

5. Haga clic en **Descargar paquete** y guarde el archivo. zip.

6. Copie los archivos de la carpeta DeviceCompliancePackage extraídos del archivo. zip en la `golden/master` imagen de la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

7. Si no va a implementar una entrada única para cada dispositivo, copie DeviceComplianceOnboardingScript. cmd.

8. Si va a implementar una entrada única para cada dispositivo, copie tanto Onboard-NonPersistentMachine.ps1 como DeviceComplianceOnboardingScript. cmd.
    
    > [!NOTE]
    > Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, es posible que esté oculta. Deberá elegir la opción **Mostrar todos los archivos y carpetas ocultos** en el explorador de archivos.

9. Abra una ventana del editor de directivas de grupo local y desplácese hasta **configuración del equipo**  >  **Windows**  >  **scripts**  >  **Startup** .

   > [!NOTE]
   > La Directiva de grupo de dominio también puede usarse para incorporar dispositivos no persistentes de VDI no persistentes.

4. Según el método que quiera implementar, siga los pasos apropiados:

   **Para una entrada única para cada dispositivo**
   
   Seleccione la pestaña **scripts de PowerShell** y haga clic en **Agregar** (el explorador de Windows se abrirá directamente en la ruta de acceso donde copió anteriormente el script de incorporación). Navegue al script de PowerShell de incorporación `Onboard-NonPersistentMachine.ps1` .
   
   **Para varias entradas para cada dispositivo** :
   
   Seleccione la pestaña **scripts** y, a continuación, haga clic en **Agregar** (el explorador de Windows se abrirá directamente en la ruta de acceso donde copió el script de incorporación, anteriormente). Navegue hasta el script de la bash de incorporación `DeviceComplianceOnboardingScript.cmd` .

5. Pruebe la solución:

   1. Cree un grupo de servidores con un dispositivo.
      
   1. Inicie sesión en el dispositivo.
      
   1. Cierre la sesión del dispositivo.

   1. Inicie sesión en el dispositivo con otro usuario.
      
   1. **Para una entrada única para cada dispositivo** : Compruebe solo una entrada en el centro de seguridad de Microsoft defender.<br>
      **Para varias entradas para cada dispositivo** : Compruebe varias entradas en el centro de seguridad de Microsoft defender.

6. Haga clic en **lista de dispositivos** en el panel de navegación.

7. Use la función de búsqueda escribiendo el nombre del dispositivo y seleccione **dispositivo** como tipo de búsqueda.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistentes
Como procedimiento recomendado, se recomienda el uso de herramientas de servicio sin conexión para aplicar revisiones a imágenes maestras o en oro.<br>
Por ejemplo, puede usar los comandos siguientes para instalar una actualización mientras la imagen permanece sin conexión:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obtener más información acerca de los comandos de DISM y el servicio sin conexión, consulte los artículos siguientes:
- [Modificación de una imagen de Windows mediante DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opciones de Command-Line de administración de imágenes de DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reducir el tamaño del almacén de componentes en una imagen de Windows sin conexión](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Si el mantenimiento sin conexión no es una opción viable para el entorno de la VDI no persistente, debe seguir estos pasos para garantizar la coherencia y el estado de los sensores:

1. Después de arrancar la imagen maestra para el servicio en línea o la revisión, ejecute un script de descarga para desactivar el sensor de prevención de pérdida de datos de extremos de Microsoft 365. Para obtener más información, vea [desincorpora dispositivos con un script local](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).

2. Asegúrese de detener el sensor ejecutando el comando siguiente en una ventana de CMD:

   ```console
   sc query sense
   ```

3. Servicio de la imagen según sea necesario.

4. Ejecute los siguientes comandos con PsExec.exe (que se puede descargar de https://download.sysinternals.com/files/PSTools.zip) para limpiar el contenido de la carpeta Cyber que el sensor puede haber acumulado desde el inicio:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Vuelva a sellar la imagen Golden/Master como lo haría normalmente.

## <a name="related-topics"></a>Temas relacionados
- [Dispositivos de Windows 10 incorporados mediante la Directiva de grupo](dlp-configure-endpoints-gp.md)
- [Dispositivos con Windows 10 en placa mediante el administrador de configuración de Microsoft Endpoint](dlp-configure-endpoints-sccm.md)
- [Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Dispositivos de Windows 10 incorporados que usan un script local](dlp-configure-endpoints-script.md)
- [Solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
