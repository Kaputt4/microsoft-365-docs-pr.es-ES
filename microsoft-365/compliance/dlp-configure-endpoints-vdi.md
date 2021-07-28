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
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que se incorpore al servicio de prevención de pérdida de datos Microsoft 365 endpoint.
ms.openlocfilehash: 1e4987ba2d261c715395ed1869f597da91b5cfed
ms.sourcegitcommit: 346c1332e1e9eebb5c90d6b8553dd70fcabf530a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53567325"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-devices"></a>Incorporación de dispositivos de infraestructura de escritorio virtual no persistentes

**Se aplica a:**
- [Microsoft 365 Prevención de pérdida de datos de extremo (DLP)](./endpoint-dlp-learn-about.md)

- Dispositivos de infraestructura de escritorio virtual (VDI)

> [!WARNING]
> Microsoft 365 La compatibilidad de prevención de pérdida de datos de puntos de conexión Windows Escritorio virtual admite escenarios de sesión única. Actualmente, no se admiten Windows escenarios de varias sesiones en Escritorio virtual.

## <a name="onboard-vdi-devices"></a>Incorporar dispositivos VDI

Microsoft 365 La prevención de pérdida de datos de extremo admite la incorporación de sesiones de infraestructura de escritorio virtual (VDI) no persistente.

> [!NOTE]
> Para incorporar sesiones VDI no persistentes, los dispositivos VDI deben estar en Windows 10 1809 o posterior.

Puede haber desafíos asociados al incorporar LOS VDIs. Los siguientes son los desafíos típicos de este escenario:

- Incorporación instantánea y anticipada de sesiones de corta duración, que deben incorporarse a Microsoft 365 prevención de pérdida de datos del punto de conexión antes del aprovisionamiento real.
- El nombre del dispositivo normalmente se reutiliza para nuevas sesiones.

Los dispositivos VDI pueden aparecer en el centro Microsoft 365 cumplimiento como:

- Entrada única para cada dispositivo.
Tenga en cuenta que, en este caso, *debe* configurarse el mismo nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendido.
- Varias entradas para cada dispositivo: una para cada sesión.

Los siguientes pasos le guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.

> [!WARNING]
> En los entornos en los que hay configuraciones de recursos bajos, el procedimiento de arranque de VDI puede ralentizar la incorporación Microsoft 365 prevención de pérdida de datos del punto de conexión.

1. Abra el archivo de configuración .zip VDI (*DeviceCompliancePackage.zip*) que descargó del Asistente para incorporación de servicios.

2. En el panel de navegación, **seleccione Configuración** Incorporación  >  **de**  >  **dispositivos**.

3. En el **campo Método de** implementación, seleccione Scripts de incorporación de VDI para puntos de conexión no **persistentes.**

4. Haga **clic en Descargar paquete** y guarde el .zip archivo.

5. Copie los archivos de la carpeta DeviceCompliancePackage extraídos del archivo .zip en la `golden/master` imagen debajo de la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .

6. Si no implementa una sola entrada para cada dispositivo, copie DeviceComplianceOnboardingScript.cmd.

7. Si va a implementar una sola entrada para cada dispositivo, copie tanto Onboard-NonPersistentMachine.ps1 como DeviceComplianceOnboardingScript.cmd.

    > [!NOTE]
    > Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, podría estar oculta. Tendrás que elegir la opción Mostrar **archivos y carpetas** ocultos en el Explorador de archivos.

8. Abra una ventana Editor de directivas de grupo local y vaya a **Configuración** del  >  **equipo Windows Configuración** inicio de  >    >  **scripts.**

   > [!NOTE]
   > La directiva de grupo de dominio también se puede usar para incorporar dispositivos VDI no persistentes.

9. Según el método que quiera implementar, siga los pasos correspondientes:

   **Para una sola entrada para cada dispositivo**

   Seleccione la **pestaña Scripts de PowerShell** y, a continuación, haga clic en Agregar **(el** Explorador de Windows se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente). Navegue a la incorporación del script de PowerShell `Onboard-NonPersistentMachine.ps1` .

   **Para varias entradas para cada dispositivo:**

   Seleccione la **pestaña Scripts** y, a continuación, haga clic en Agregar **(Windows** Explorer se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente). Vaya al script bash de incorporación `DeviceComplianceOnboardingScript.cmd` .

10. Pruebe la solución:
    1. Crea un grupo de servidores con un dispositivo.
    1. Inicie sesión en el dispositivo.
    1. Cierre sesión desde el dispositivo.
    1. Inicie sesión en el dispositivo con otro usuario.
    1. **Para una sola entrada para cada dispositivo:** compruebe solo una entrada en Centro de seguridad de Microsoft Defender.
       **Para varias entradas para cada dispositivo:** compruebe varias entradas en Centro de seguridad de Microsoft Defender.

11. Haga **clic en Lista de** dispositivos en el panel de navegación.

12. Para usar la función de búsqueda, escriba el nombre del dispositivo y seleccione **Dispositivo** como tipo de búsqueda.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistente

Como práctica recomendada, se recomienda usar herramientas de mantenimiento sin conexión para aplicar revisiones a imágenes doradas o maestras.

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

1. Después de arrancar la imagen maestra para el mantenimiento en línea o la revisión, ejecute un script de offboarding para desactivar el sensor de prevención de pérdida de datos Microsoft 365 endpoint. Para obtener más información, vea [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).

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

- [Incorporación Windows 10 dispositivos con directiva de grupo](dlp-configure-endpoints-gp.md)
- [Incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](dlp-configure-endpoints-script.md)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
