---
title: Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que se incorporen a Microsoft Defender para punto de conexión servicio.
keywords: configurar el dispositivo de infraestructura de escritorio virtual (VDI), vdi, administración de dispositivos, configurar Microsoft Defender para punto de conexión, puntos de conexión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.date: 04/15/2022
ms.technology: mde
ms.openlocfilehash: 8bf3dda061b582adb7b21029022e61bc890aeec7
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441648"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-in-microsoft-365-defender"></a>Incorporación de dispositivos de infraestructura de escritorio virtual (VDI) no persistente en Microsoft 365 Defender

La infraestructura de escritorio virtual (VDI) es un concepto de infraestructura de TI que permite a los usuarios finales acceder a instancias de escritorios virtuales empresariales desde casi cualquier dispositivo (como su equipo personal, smartphone o tableta), lo que elimina la necesidad de que la organización proporcione a los usuarios máquinas físicas. El uso de dispositivos VDI reduce el costo, ya que los departamentos de TI ya no son responsables de administrar, reparar y reemplazar puntos de conexión físicos. Los usuarios autorizados pueden acceder a los mismos servidores, archivos, aplicaciones y servicios de la empresa desde cualquier dispositivo aprobado a través de un explorador o cliente de escritorio seguro.

Al igual que cualquier otro sistema de un entorno de TI, estos también deben tener una solución antivirus y de detección de puntos de conexión (EDR) para protegerse frente a amenazas y ataques avanzados.


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Dispositivos de infraestructura de escritorio virtual (VDI)
- Windows 10, Windows 11, Windows Server 2019, Windows Server 2022, Windows Server 2008R2/2012R2/2016


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configvdi-abovefoldlink)

 > [!NOTE]
  > **VDI persistentes**: la incorporación de una máquina VDI persistente a Microsoft Defender para punto de conexión se controla de la misma manera que incorporaría una máquina física, como un equipo de escritorio o portátil. La directiva de grupo, Microsoft Endpoint Manager y otros métodos se pueden usar para incorporar una máquina persistente. En el portal de Microsoft 365 Defender, (https://security.microsoft.com) en incorporación, seleccione el método de incorporación que prefiera y siga las instrucciones de ese tipo. Para obtener más información, consulte [Incorporación del cliente Windows](onboard-windows-client.md).

## <a name="onboarding-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Incorporación de dispositivos de infraestructura de escritorio virtual (VDI) no persistentes

Defender for Endpoint admite la incorporación de sesión de VDI no persistente.

Puede haber desafíos asociados al incorporar instancias de VDI. Los siguientes son los desafíos típicos de este escenario:

- Incorporación temprana instantánea de una sesión de corta duración, que debe incorporarse a Defender para punto de conexión antes del aprovisionamiento real.
- Normalmente, el nombre del dispositivo se reutiliza para las sesiones nuevas.

En un entorno de VDI, las instancias de VDI pueden tener una duración corta. Los dispositivos VDI pueden aparecer en el portal de Defender para punto de conexión como:


- Entrada de portal única para cada instancia de VDI. Si la instancia de VDI ya se ha incorporado a Microsoft Defender para punto de conexión y, en algún momento, se ha eliminado y, a continuación, se vuelve a crear con el mismo nombre de host, no se creará un nuevo objeto que represente esta instancia de VDI en el portal. 

  > [!NOTE]
  > En este caso, se debe configurar el *mismo* nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendida.

- Varias entradas para cada dispositivo: una para cada instancia de VDI.

Los pasos siguientes le guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.

> [!WARNING]
> En entornos en los que hay configuraciones de recursos bajas, el procedimiento de arranque de VDI podría ralentizar la incorporación del sensor de Defender para punto de conexión.

### <a name="onboarding-steps"></a>Pasos de incorporación

> [!NOTE]
> Windows Server 2016 y Windows Server 2012 R2 deben prepararse aplicando primero el paquete de instalación mediante las instrucciones de [Incorporación de servidores Windows](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2012-r2-and-windows-server-2016) para que esta característica funcione.

1.  Abra el archivo de .zip del paquete de configuración de VDI (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del asistente para la incorporación de servicios. También puede obtener el paquete desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>:

    1. En el panel de navegación, seleccione **Configuración** > **Puntos de conexión** > **Incorporación** **de administración de** >  dispositivos.

    1. Seleccione el sistema operativo.

    1.  En el campo **Método de implementación** , seleccione **Scripts de incorporación de VDI para puntos de conexión no persistentes**.

    1. Haga clic en **Descargar paquete** y guarde el archivo .zip.

2. Copie los archivos de la carpeta WindowsDefenderATPOnboardingPackage extraída del archivo .zip en la imagen maestra o dorada de la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.
    1. Si va a implementar varias entradas para cada dispositivo, una para cada sesión, copie WindowsDefenderATPOnboardingScript.cmd.
    2. Si va a implementar una única entrada para cada dispositivo, copie Onboard-NonPersistentMachine.ps1 y WindowsDefenderATPOnboardingScript.cmd.

    > [!NOTE]
    > Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, es posible que esté oculta. Tendrá que elegir la opción **Mostrar archivos y carpetas ocultos** de Explorador de archivos.

3. Abra una ventana Editor de directiva de grupo local y vaya a **Configuración** \> del equipo **Scripts** \> **de Configuración de** \> Windows **Inicio**.

   > [!NOTE]
   > Los directiva de grupo de dominio también se pueden usar para la incorporación de dispositivos VDI no persistentes.

4. En función del método que quiera implementar, siga los pasos adecuados:
    - Para una sola entrada para cada dispositivo:

         Seleccione la pestaña **Scripts de PowerShell** y haga clic en **Agregar** (el Explorador de Windows se abrirá directamente en la ruta de acceso donde copió el script de incorporación anteriormente). Vaya a incorporación del script `Onboard-NonPersistentMachine.ps1`de PowerShell. No es necesario especificar el otro archivo, ya que se desencadenará automáticamente.

    - Para varias entradas para cada dispositivo:

         Seleccione la pestaña **Scripts** y haga clic en **Agregar** (el Explorador de Windows se abrirá directamente en la ruta de acceso donde copió el script de incorporación anteriormente). Vaya al script `WindowsDefenderATPOnboardingScript.cmd`de Bash de incorporación.

5. Pruebe la solución:
   1. Cree un grupo con un dispositivo.
   2. Inicie sesión en el dispositivo.
   3. Cierre la sesión del dispositivo.
   4. Inicie sesión en el dispositivo con otro usuario.
   5. En función del método que quiera implementar, siga los pasos adecuados:
      - Para una sola entrada para cada dispositivo: compruebe solo una entrada en Microsoft 365 Defender portal.
      - Para varias entradas para cada dispositivo: compruebe varias entradas en Microsoft 365 Defender portal.

6. Haga clic en **la lista Dispositivos** en el panel de navegación.

7. Para usar la función de búsqueda, escriba el nombre del dispositivo y seleccione **Dispositivo** como tipo de búsqueda.

## <a name="for-downlevel-skus-windows-server-2008-r2"></a>Para SKU de nivel inferior (Windows Server 2008 R2)

> [!NOTE]
> Estas instrucciones para otras versiones de Windows Server también se aplican si ejecuta la Microsoft Defender para punto de conexión anterior para Windows Server 2016 y Windows Server 2012 R2 que requiere el MMA. Las instrucciones para migrar a la nueva solución unificada se encuentran [en escenarios de migración del servidor en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/server-migration).

> [!NOTE]
> El registro siguiente solo es relevante cuando el objetivo es lograr una "entrada única para cada dispositivo".

1. Establezca el valor del Registro en:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    o mediante la línea de comandos:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. Siga el [proceso de incorporación del servidor](configure-server-endpoints.md). 

## <a name="updating-virtual-desktop-infrastructure-vdi-images-persistent-or-non-persistent"></a>Actualización de imágenes de infraestructura de escritorio virtual (VDI) (persistentes o no persistentes)

Con la capacidad de implementar fácilmente actualizaciones en máquinas virtuales que se ejecutan en VDIs, hemos acortado esta guía para centrarse en cómo puede obtener actualizaciones en las máquinas de forma rápida y sencilla. Ya no es necesario crear y sellar imágenes doradas periódicamente, ya que las actualizaciones se expanden en sus bits de componente en el servidor host y, a continuación, se descargan directamente en la máquina virtual cuando está activada.

Para obtener más información, siga las instrucciones de la [Guía de implementación de Antivirus de Microsoft Defender en un entorno de Infraestructura de escritorio virtual (VDI).](/microsoft-365/security/defender-endpoint/deployment-vdi-microsoft-defender-antivirus)

   > [!NOTE]
   > Si ha incorporado la imagen maestra del entorno de VDI (se está ejecutando el servicio SENSE), debe desconectar y borrar algunos datos antes de volver a poner la imagen en producción.
   > 1. Asegúrese de que el sensor se detiene ejecutando el siguiente comando en una ventana CMD:
   >  ```console
   >  sc query sense
   >  ```
   > 2. Ejecute los comandos siguientes mediante PsExec.exe (que se pueden descargar desde https://download.sysinternals.com/files/PSTools.zip)
   >
   >  ```console
   >  PsExec.exe -s cmd.exe
   >  cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
   >  del *.* /f /s /q
   >  REG DELETE "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
   >  exit
   >  ```

## <a name="other-recommended-configuration-settings"></a>Otras opciones de configuración recomendadas

Después de incorporar dispositivos al servicio, es importante aprovechar las funcionalidades de protección contra amenazas incluidas al habilitarlos con las siguientes opciones de configuración recomendadas.

### <a name="next-generation-protection-configuration"></a>Configuración de protección de próxima generación

Se recomiendan los siguientes valores de configuración:

#### <a name="cloud-protection-service"></a>Servicio de protección en la nube

- Activar la protección proporcionada en la nube: Sí
- Nivel de protección proporcionada en la nube: no configurado
- Tiempo de espera extendido en la nube de Defender en segundos: 20

#### <a name="exclusions"></a>Exclusiones
- Deshabilitar combinación de administración local: no configurado
- Procesos de Defender que se van a excluir:
  - `%Programfiles%\FSLogix\Apps\frxccd.exe`
  - `%Programfiles%\FSLogix\Apps\frxccds.exe`
  - `%Programfiles%\FSLogix\Apps\frxsvc.exe`

- Extensiones de archivo para excluir de exámenes y protección en tiempo real:
  -  `%Programfiles%\FSLogix\Apps\frxccd.sys`
  - `%Programfiles%\FSLogix\Apps\frxdrv.sys`
  - `%Programfiles%\FSLogix\Apps\frxdrvvt.sys`
  - `%TEMP%*.VHD`
  - `%TEMP%*.VHDX`
  - `%Windir%\TEMP*.VHD`
  - `%Windir%\TEMP*.VHDX`
  - `\\stroageaccount.file.core.windows.net\share**.VHD`
  -  `\\stroageaccount.file.core.windows.net\share**.VHDX`

#### <a name="real-time-protection"></a>Protección en tiempo real

- Activar toda la configuración y establecer para supervisar todos los archivos

#### <a name="remediation"></a>Remediación
- Número de días para mantener el malware en cuarentena: 30
- Enviar consentimiento de ejemplos: enviar todas las muestras automáticamente
- Acción a realizar sobre las aplicaciones potencialmente no deseadas: habilitar
- Acciones para las amenazas detectadas:
  - Amenaza baja: Limpiar
  - Amenaza moderada, Amenaza alta, Amenaza grave: Cuarentena

#### <a name="scan"></a>Examinar

- Examinar archivos archivados: Sí
- Uso de prioridad de CPU baja para exámenes programados: No configurado
- Deshabilitar el examen completo de puesta al día: No configurado
- Deshabilitación del examen rápido de captura: no configurado
- Límite de uso de CPU por examen: 50
- Examen de unidades netoword asignadas durante el examen completo: No configurado
- Ejecución del examen rápido diario a las 12 p. m.
- Tipo de examen: no configurado
- Día de la semana para ejecutar el examen programado: No configurado
- Hora del día para ejecutar un examen programado: No configurado
- Comprobación de actualizaciones de firmas antes de ejecutar el examen: Sí

#### <a name="updates"></a>Actualizaciones
- Escriba la frecuencia con la que comprobar si hay actualizaciones de inteligencia de seguridad: 8
- Deje otras opciones de configuración en estado predeterminado.

#### <a name="user-experience"></a>Experiencia del usuario
- Permitir el acceso del usuario a la aplicación Microsoft Defender: No configurado

#### <a name="enable-tamper-protection"></a>Habilitación de la protección contra alteraciones
- Habilitar la protección contra alteraciones para evitar que Microsoft Defender se deshabilite: Habilitar

#### <a name="attack-surface-reduction"></a>Reducción de la superficie expuesta a ataques

- Habilitación de la protección de red: modo de auditoría
- Requerir SmartScreen para Microsoft Edge: Sí
- Bloquear el acceso a sitios malintencionados: Sí
- Bloquear la descarga de archivos no comprobados: Sí

#### <a name="attack-surface-reduction-rules"></a>Reglas de reducción de la superficie expuesta a ataques
- Configure todas las reglas disponibles en Auditar.

> [!NOTE]
> Bloquear estas actividades puede interrumpir procesos empresariales legítimos. El mejor enfoque es establecer todo para auditar, identificar cuáles son seguras de activar y, a continuación, habilitar esa configuración en puntos de conexión que no tienen detecciones de falsos positivos.

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows mediante directiva de grupo](configure-endpoints-gp.md)
- [Incorporar dispositivos Windows mediante Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows mediante herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows mediante un script local](configure-endpoints-script.md)
- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
