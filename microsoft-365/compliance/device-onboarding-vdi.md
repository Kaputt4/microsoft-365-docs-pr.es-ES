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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que se incorporen al servicio de prevención de pérdida de datos del punto de conexión.
ms.openlocfilehash: 8a54d4ce3cfb4b3ba6571f2aee63cd60c2a6d71f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636147"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-devices"></a>Incorporación de dispositivos de infraestructura de escritorio virtual no persistentes

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)

- Dispositivos de infraestructura de escritorio virtual (VDI)

> [!WARNING]
> La compatibilidad con la prevención de pérdida de datos de punto de conexión para Windows Virtual Desktop admite escenarios de sesión única. Actualmente no se admiten escenarios de varias sesiones en Windows Virtual Desktop.

## <a name="onboard-vdi-devices"></a>Incorporación de dispositivos VDI

Microsoft 365 admite la incorporación de sesión de infraestructura de escritorio virtual (VDI) no persistente.

> [!NOTE]
> Para incorporar sesiones de VDI no persistentes, los dispositivos VDI deben estar en Windows 10 1809 o superior.

Es posible que haya desafíos asociados al incorporar los V VDI. Los siguientes son los desafíos típicos de este escenario:

- Incorporación temprana instantánea de sesiones de corta duración, que deben incorporarse a Microsoft 365 antes del aprovisionamiento real.
- Normalmente, el nombre del dispositivo se reutiliza para las sesiones nuevas.

Los dispositivos VDI pueden aparecer en el portal de cumplimiento Microsoft Purview como:

- Entrada única para cada dispositivo.
Tenga en cuenta que, en este caso, se debe configurar el *mismo* nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendida.
- Varias entradas para cada dispositivo: una para cada sesión.

Los pasos siguientes le guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.

> [!WARNING]
> En entornos en los que hay configuraciones de recursos bajas, el procedimiento de arranque de VDI podría ralentizar el proceso de incorporación de dispositivos.

1. Obtenga el archivo de .zip del paquete de configuración de VDI (*DeviceCompliancePackage.zip*) de [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com).

2. En el panel de navegación, seleccione **Configuración Incorporación** > **de** > **dispositivos.**

3. En el campo **Método de implementación** , seleccione **Scripts de incorporación de VDI para puntos de conexión no persistentes**.

4. Haga clic en **Descargar paquete** y guarde el archivo .zip.

5. Copie los archivos de la carpeta DeviceCompliancePackage extraídos del archivo .zip en la `golden` imagen de la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.

6. Si no va a implementar una sola entrada para cada dispositivo, copie DeviceComplianceOnboardingScript.cmd.

7. Si va a implementar una única entrada para cada dispositivo, copie Onboard-NonPersistentMachine.ps1 y DeviceComplianceOnboardingScript.cmd.

    > [!NOTE]
    > Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, es posible que esté oculta. Tendrá que elegir la opción **Mostrar archivos y carpetas ocultos** de Explorador de archivos.

8. Abra una ventana Editor de directiva de grupo local y vaya a Configuración  > **del equipo****Scripts** > **de Configuración de** >  Windows **Inicio**.

   > [!NOTE]
   > Los directiva de grupo de dominio también se pueden usar para la incorporación de dispositivos VDI no persistentes.

9. En función del método que quiera implementar, siga los pasos adecuados:

   **Para una sola entrada para cada dispositivo**

   Seleccione la pestaña **Scripts de PowerShell** y haga clic en **Agregar** (el Explorador de Windows se abrirá directamente en la ruta de acceso donde copió el script de incorporación anteriormente). Vaya a incorporación del script `Onboard-NonPersistentMachine.ps1`de PowerShell.

   **Para varias entradas para cada dispositivo**:

   Seleccione la pestaña **Scripts** y haga clic en **Agregar** (el Explorador de Windows se abrirá directamente en la ruta de acceso donde copió el script de incorporación anteriormente). Vaya al script `DeviceComplianceOnboardingScript.cmd`de Bash de incorporación.

10. Pruebe la solución:
    1. Cree un grupo con un dispositivo.
    1. Inicie sesión en el dispositivo.
    1. Cierre la sesión del dispositivo.
    1. Inicie sesión en el dispositivo con otro usuario.
    1. **Para una sola entrada para cada dispositivo**: compruebe solo una entrada en Centro de seguridad de Microsoft Defender.
       **Para varias entradas para cada dispositivo**: compruebe varias entradas en Centro de seguridad de Microsoft Defender.

11. Haga clic en **la lista Dispositivos** en el panel de navegación.

12. Para usar la función de búsqueda, escriba el nombre del dispositivo y seleccione **Dispositivo** como tipo de búsqueda.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistentes

Como procedimiento recomendado, se recomienda usar herramientas de mantenimiento sin conexión para aplicar revisiones a las imágenes doradas.

Por ejemplo, puede usar los siguientes comandos para instalar una actualización mientras la imagen permanece sin conexión:

```DOS
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obtener más información sobre los comandos DISM y el mantenimiento sin conexión, consulte los artículos siguientes:

- [Modificación de una imagen de Windows mediante DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opciones de Command-Line DISM Image Management](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reducir el tamaño del almacén de componentes en una imagen de Windows sin conexión](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Si el mantenimiento sin conexión no es una opción viable para el entorno de VDI no persistente, se deben realizar los pasos siguientes para garantizar la coherencia y el estado del sensor:

1. Después de arrancar la imagen dorada para el mantenimiento en línea o la aplicación de revisiones, ejecute un script de offboarding para desactivar el sensor de supervisión de dispositivos de Microsoft 365. Para obtener más información, consulte [Dispositivos fuera del panel con un script local](device-onboarding-script.md#offboard-devices-using-a-local-script).

2. Asegúrese de que el sensor se detiene ejecutando el siguiente comando en una ventana CMD:

   ```DOS
   sc query sense
   ```

3. Servicio de la imagen según sea necesario.

4. Ejecute los comandos siguientes mediante PsExec.exe (que se pueden descargar desde para limpiar el contenido de https://download.sysinternals.com/files/PSTools.zip) la carpeta cibernética que el sensor puede haber acumulado desde el arranque:

    ```DOS
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Vuelva a sellar la imagen dorada como lo haría normalmente.

## <a name="related-topics"></a>Temas relacionados

- [Incorporación de dispositivos Windows 10 y Windows 11 mediante directiva de grupo](device-onboarding-gp.md)
- [Incorporación de dispositivos Windows 10 y Windows 11 mediante Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [Incorporar dispositivos Windows 10 y Windows 11 con herramientas de Administración de dispositivos móviles](device-onboarding-mdm.md)
- [Incorporar dispositivos Windows 10 y Windows 11 mediante un script local](device-onboarding-script.md)
- [Solución de problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
