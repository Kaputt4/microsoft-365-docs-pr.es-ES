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
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769511"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente

**Se aplica a:**
- [Prevención de pérdida de datos (DLP) de Punto de conexión de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)

- Dispositivos de infraestructura de escritorio virtual (VDI)

>[!WARNING]
> Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios. Actualmente no se admiten escenarios de varias sesiones en Windows Virtual Desktop.

## <a name="onboard-vdi-devices"></a>Incorporar dispositivos VDI

La prevención de pérdida de datos de puntos de conexión de Microsoft 365 admite la incorporación de sesiones de VDI no persistentes. 

>[!Note]
>Para incorporar sesiones de VDI no persistentes, los dispositivos VDI deben estar en Windows 10 1809 o versiones posteriores.

Es posible que haya desafíos asociados al incorporar los VDIs. Los siguientes son los desafíos típicos para este escenario:

- Incorporación anticipada instantánea de sesiones de corta duración, que deben incorporarse a la prevención de pérdida de datos del punto de conexión de Microsoft 365 antes del aprovisionamiento real.
- El nombre del dispositivo se suele reutilizar para las sesiones nuevas.

Los dispositivos VDI pueden aparecer en el Centro de cumplimiento de Microsoft 365 como:

- Entrada única para cada dispositivo.  
Ten en cuenta que, en este caso, *debe* configurarse el mismo nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendido.
- Varias entradas para cada dispositivo: una para cada sesión.

Los siguientes pasos te guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.

>[!WARNING]
> Para entornos en los que hay configuraciones de recursos bajos, el procedimiento de arranque de VDI podría ralentizar la incorporación de la prevención de pérdida de datos de Puntos de conexión de Microsoft 365. 

1.  Abre el archivo .zip del paquete de configuración VDI (*DeviceCompliancePackage.zip*) que descargaste desde el Asistente para la incorporación de servicios.

2.  En el panel de navegación, selecciona **Configuración**  >  **de incorporación de**  >  **dispositivos.**

3. En el **campo Método de** implementación, seleccione scripts de incorporación de **VDI para extremos no persistentes.**

5. Haz **clic en Descargar paquete** y guarda el archivo .zip.

6. Copie los archivos de la carpeta DeviceCompliancePackage extraídos del archivo .zip en la `golden/master` imagen bajo la ruta de `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` acceso. 

7. Si no vas a implementar una sola entrada para cada dispositivo, copia DeviceComplianceOnboardingScript.cmd.

8. Si vas a implementar una sola entrada para cada dispositivo, copia tanto Onboard-NonPersistentMachine.ps1 como DeviceComplianceOnboardingScript.cmd.
    
    > [!NOTE]
    > Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, es posible que esté oculta. Tendrás que elegir la opción Mostrar archivos **y** carpetas ocultos en el Explorador de archivos.

9. Abra una ventana del Editor de directivas de grupo local y vaya a Configuración **del** equipo Inicio de scripts  >  **de configuración**  >  **de**  >  **Windows**.

   > [!NOTE]
   > La directiva de grupo de dominio también se puede usar para incorporar dispositivos VDI no persistentes.

4. En función del método que quieras implementar, sigue los pasos adecuados:

   **Para una sola entrada para cada dispositivo**
   
   Selecciona la pestaña Scripts de **PowerShell** y, a continuación, haz clic en Agregar **(el** Explorador de Windows se abrirá directamente en la ruta de acceso donde has copiado el script de incorporación anteriormente). Vaya al script de PowerShell de `Onboard-NonPersistentMachine.ps1` incorporación.
   
   **Para varias entradas para cada dispositivo:**
   
   Selecciona la **pestaña Scripts** y, a continuación, haz clic en Agregar **(el** Explorador de Windows se abrirá directamente en la ruta de acceso donde has copiado el script de incorporación anteriormente). Navegue al script bash de `DeviceComplianceOnboardingScript.cmd` incorporación.

5. Pruebe la solución:

   1. Crea un grupo de servidores con un dispositivo.
      
   1. Inicie sesión en el dispositivo.
      
   1. Cierre la sesión del dispositivo.

   1. Inicie sesión en el dispositivo con otro usuario.
      
   1. **Para una sola entrada para cada dispositivo:** compruebe solo una entrada en el Centro de seguridad de Microsoft Defender.<br>
      **Para varias entradas para cada dispositivo:** compruebe varias entradas en el Centro de seguridad de Microsoft Defender.

6. Haga **clic en la lista Dispositivos** en el panel de navegación.

7. Para usar la función de búsqueda, escribe el nombre del dispositivo y selecciona **Dispositivo** como tipo de búsqueda.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistente
Como procedimiento recomendado, se recomienda usar herramientas de mantenimiento sin conexión para aplicar revisiones a imágenes maestras o de oro.<br>
Por ejemplo, puedes usar los siguientes comandos para instalar una actualización mientras la imagen permanece sin conexión:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obtener más información sobre los comandos DISM y el mantenimiento sin conexión, consulta los artículos siguientes:
- [Modificar una imagen de Windows con DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opciones de administración de imágenes Command-Line DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reducir el tamaño del almacén de componentes en una imagen de Windows sin conexión](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Si el mantenimiento sin conexión no es una opción viable para el entorno de VDI no persistente, se deben realizar los siguientes pasos para garantizar la coherencia y el estado del sensor:

1. Después de arrancar la imagen maestra para el mantenimiento en línea o la revisión, ejecute un script de descarga para desactivar el sensor de prevención de pérdida de datos del punto de conexión de Microsoft 365. Para obtener más información, vea [Dispositivos de fuera de la oficina con un script local.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)

2. Asegúrate de que el sensor se detiene ejecutando el siguiente comando en una ventana cmd:

   ```console
   sc query sense
   ```

3. Servicio de la imagen según sea necesario.

4. Ejecuta los siguientes comandos con PsExec.exe (que se pueden descargar para limpiar el contenido de la carpeta cibernética que el sensor haya acumulado https://download.sysinternals.com/files/PSTools.zip) desde el arranque:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Vuelva a sellar la imagen de patrón o dorado como lo haría normalmente.

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows 10 mediante la directiva de grupo](dlp-configure-endpoints-gp.md)
- [Incorporar dispositivos Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](dlp-configure-endpoints-script.md)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
