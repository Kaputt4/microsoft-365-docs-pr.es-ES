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
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que se incorpore al servicio de prevención de pérdida de datos de Microsoft 365 endpoint.
ms.openlocfilehash: 00804c93022f21715e3604eeb45c22caa4745f91
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682160"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-devices"></a>Incorporación de dispositivos de infraestructura de escritorio virtual no persistentes

**Se aplica a:**

- [Prevención de pérdida de datos en punto de conexión en Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

- Dispositivos de infraestructura de escritorio virtual (VDI)

> [!WARNING]
> Microsoft 365 de prevención de pérdida de datos del punto de conexión para Windows Virtual Desktop admite escenarios de sesión única. Actualmente, no se admiten escenarios de varias Windows virtual desktop.

## <a name="onboard-vdi-devices"></a>Incorporar dispositivos VDI

Microsoft 365 admite la incorporación de sesiones de infraestructura de escritorio virtual (VDI) no persistente.

> [!NOTE]
> Para incorporar sesiones VDI no persistentes, los dispositivos VDI deben estar en Windows 10 1809 o posterior.

Puede haber desafíos asociados al incorporar LOS VDIs. Los siguientes son los desafíos típicos de este escenario:

- Incorporación anticipada instantánea de sesiones de corta duración, que deben incorporarse a Microsoft 365 antes del aprovisionamiento real.
- El nombre del dispositivo normalmente se reutiliza para nuevas sesiones.

Los dispositivos VDI pueden aparecer en el centro Microsoft 365 cumplimiento como:

- Entrada única para cada dispositivo.
Tenga en cuenta que, en este caso *, debe* configurarse el mismo nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendido.
- Varias entradas para cada dispositivo: una para cada sesión.

Los siguientes pasos le guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.

> [!WARNING]
> En los entornos donde hay configuraciones de recursos bajos, el procedimiento de arranque de VDI puede ralentizar el proceso de incorporación del dispositivo.

1. Obtenga el paquete de configuración VDI .zip archivo (*DeviceCompliancePackage.zip*) del [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com).

2. En el panel de navegación, **seleccione Configuración** >  **Device onboardingOnboarding** > .

3. En el **campo Método de** implementación, seleccione **Scripts de incorporación de VDI para puntos de conexión no persistentes**.

4. Haga **clic en Descargar paquete** y guarde el .zip archivo.

5. Copie los archivos de la carpeta DeviceCompliancePackage extraída del archivo .zip en `golden` la imagen de la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.

6. Si no implementa una sola entrada para cada dispositivo, copie DeviceComplianceOnboardingScript.cmd.

7. Si va a implementar una sola entrada para cada dispositivo, copie tanto Onboard-NonPersistentMachine.ps1 como DeviceComplianceOnboardingScript.cmd.

    > [!NOTE]
    > Si no ve la carpeta `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` , podría estar oculta. Tendrás que elegir la opción Mostrar **archivos y carpetas** ocultos en el Explorador de archivos.

8. Abra una ventana del Editor de directivas de grupo local y vaya a **Configuración** >  del **equipo Windows Configuración** >  **ScriptsStartup** > .

   > [!NOTE]
   > La directiva de grupo de dominio también se puede usar para incorporar dispositivos VDI no persistentes.

9. Según el método que quiera implementar, siga los pasos correspondientes:

   **Para una sola entrada para cada dispositivo**

   Seleccione la **pestaña Scripts de PowerShell** y, a continuación, haga clic en **Agregar (Windows** Explorer se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente). Navegue a la incorporación del script `Onboard-NonPersistentMachine.ps1`de PowerShell .

   **Para varias entradas para cada dispositivo**:

   Seleccione la **pestaña Scripts** y, a continuación, haga clic en **Agregar (Windows** Explorer se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente). Vaya al script bash de incorporación `DeviceComplianceOnboardingScript.cmd`.

10. Pruebe la solución:
    1. Crea un grupo de servidores con un dispositivo.
    1. Inicie sesión en el dispositivo.
    1. Cierre la sesión desde el dispositivo.
    1. Inicie sesión en el dispositivo con otro usuario.
    1. **Para una sola entrada para cada dispositivo**: compruebe solo una entrada en Centro de seguridad de Microsoft Defender.
       **Para varias entradas para cada dispositivo**: compruebe varias entradas en Centro de seguridad de Microsoft Defender.

11. Haga **clic en Lista de** dispositivos en el panel de navegación.

12. Para usar la función de búsqueda, escriba el nombre del dispositivo y seleccione **Dispositivo** como tipo de búsqueda.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistente

Como práctica recomendada, se recomienda usar herramientas de mantenimiento sin conexión para aplicar revisiones a imágenes doradas.

Por ejemplo, puede usar los siguientes comandos para instalar una actualización mientras la imagen permanece sin conexión:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obtener más información sobre los comandos DISM y el mantenimiento sin conexión, consulte los artículos siguientes:

- [Modificar una Windows con DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opciones de administración de imágenes Command-Line DISM](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reducir el tamaño del almacén de componentes en una imagen Windows sin conexión](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Si el mantenimiento sin conexión no es una opción viable para el entorno VDI no persistente, se deben seguir los siguientes pasos para garantizar la coherencia y el estado del sensor:

1. Después de arrancar la imagen dorada para el mantenimiento o la revisión en línea, ejecute un script de offboarding para desactivar el sensor de supervisión Microsoft 365 dispositivo. Para obtener más información, consulta [Dispositivos offboard con un script local](device-onboarding-script.md#offboard-devices-using-a-local-script).

2. Asegúrese de que el sensor está detenido ejecutando el comando siguiente en una ventana cmd:

   ```console
   sc query sense
   ```

3. Servicio de la imagen según sea necesario.

4. Ejecute los siguientes comandos con PsExec.exe ( https://download.sysinternals.com/files/PSTools.zip) que se pueden descargar para limpiar el contenido de la carpeta cibernética que el sensor puede haber acumulado desde el arranque:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Vuelva a sellar la imagen dorada como lo haría normalmente.

## <a name="related-topics"></a>Temas relacionados

- [Incorporación Windows 10 y Windows 11 dispositivos con directiva de grupo](device-onboarding-gp.md)
- [Incorporación Windows 10 y Windows 11 dispositivos con Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [Incorporar dispositivos Windows 10 y Windows 11 con herramientas de Administración de dispositivos móviles](device-onboarding-mdm.md)
- [Incorporar dispositivos Windows 10 y Windows 11 mediante un script local](device-onboarding-script.md)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
