---
title: 'Cambiar a Microsoft Defender para punto de conexión: configuración'
description: Realice el cambio a Defender para punto de conexión. Revise el proceso de instalación, que incluye la instalación de Antivirus de Microsoft Defender.
keywords: migración, Microsoft Defender para punto de conexión, antivirus, modo pasivo, proceso de configuración
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom: migrationguides
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: fe789a8f4eaaee68fd18832b5d45125407525ccd
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65873906"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Cambiar a Microsoft Defender para punto de conexión- Fase 2: Configuración

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Preparación.](images/phase-diagrams/prepare.png#lightbox)](switch-to-mde-phase-1.md)<br/>[Fase 1: Preparación](switch-to-mde-phase-1.md)|![Fase 2: Configurar.](images/phase-diagrams/setup.png#lightbox)<br/>Fase 2: Configuración|[![Fase 3: Onboard3.](images/phase-diagrams/onboard.png#lightbox)](switch-to-mde-phase-3.md)<br/>[Fase 3: Incorporación](switch-to-mde-phase-3.md)|
|---|---|---|
||*¡Estás aquí!*||

**Bienvenido a la fase de configuración del [cambio a Defender para punto de conexión](switch-to-mde-overview.md#the-migration-process)**. Esta fase incluye los pasos siguientes:

1. [Vuelva a instalar o habilitar Antivirus de Microsoft Defender en los puntos de conexión](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).
2. [Configurar Defender para punto de conexión](#configure-defender-for-endpoint).
3. [Agregue Defender para punto de conexión a la lista de exclusión de la solución existente](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution).
4. [Agregue la solución existente a la lista de exclusión para Antivirus de Microsoft Defender](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus).
5. [Configure los grupos de dispositivos, las recopilaciones de dispositivos y las unidades organizativas](#set-up-your-device-groups-device-collections-and-organizational-units).

## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>Reinstalación o habilitación de Antivirus de Microsoft Defender en los puntos de conexión

En determinadas versiones de Windows, es probable que Antivirus de Microsoft Defender se haya desinstalado o deshabilitado cuando se instaló la solución antivirus o antimalware que no es de Microsoft. Cuando los puntos de conexión que ejecutan Windows se incorporan a Defender para punto de conexión, Antivirus de Microsoft Defender pueden ejecutarse en modo pasivo junto con una solución antivirus que no sea de Microsoft. Para más información, consulte [Protección antivirus con Defender para punto de conexión](microsoft-defender-antivirus-compatibility.md#antivirus-protection-without-defender-for-endpoint).

Al realizar el cambio a Defender para punto de conexión, es posible que tenga que realizar ciertos pasos para volver a instalar o habilitar Antivirus de Microsoft Defender. En la tabla siguiente se describe qué hacer en los clientes y servidores de Windows.

|Tipo de punto de conexión|Qué hacer|
|---|---|
|Windows clientes (como puntos de conexión que ejecutan Windows 10 y Windows 11)|En general, no es necesario realizar ninguna acción para Windows clientes (a menos que se haya desinstalado Antivirus de Microsoft Defender). En general, Antivirus de Microsoft Defender deben instalarse, pero lo más probable es que se deshabiliten en este momento del proceso de migración. <br/><br/> Cuando se instala una solución antivirus o antimalware que no es de Microsoft y los clientes aún no están incorporados a Defender para punto de conexión, Antivirus de Microsoft Defender se deshabilita automáticamente. Más adelante, cuando los puntos de conexión de cliente se incorporan a Defender para punto de conexión, si esos puntos de conexión ejecutan una solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender pasa al modo pasivo. <br/><br/> Si se desinstala la solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender entra en modo activo automáticamente.|
|servidores Windows|En Windows Server, tendrá que volver a instalar Antivirus de Microsoft Defender y establecerlo en modo pasivo manualmente. En Windows servidores, cuando se instala un antivirus o antimalware que no es de Microsoft, Antivirus de Microsoft Defender no se puede ejecutar junto con la solución antivirus que no es de Microsoft. En esos casos, Antivirus de Microsoft Defender se deshabilita o desinstala manualmente. <br/><br/> Para volver a instalar o habilitar Antivirus de Microsoft Defender en Windows Server, realice las tareas siguientes: <br/>- [Vuelva a instalar Antivirus de Microsoft Defender en Windows Server 2016](#re-enable-microsoft-defender-antivirus-on-windows-server-2016)<br/>- [Vuelva a instalar Antivirus de Microsoft Defender en Windows Server, versión 1803 o posterior](#re-enable-microsoft-defender-antivirus-on-windows-server-version-1803-or-later)<br/>- [Establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server) <br/><br/>Si tiene problemas para volver a instalar o volver a habilitar Antivirus de Microsoft Defender en Windows Server, consulte [Solución de problemas: Antivirus de Microsoft Defender se desinstala en Windows Server](switch-to-mde-troubleshooting.md#microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server).|

> [!TIP]
> Para obtener más información sobre Antivirus de Microsoft Defender estados con protección antivirus que no es de Microsoft, consulte [compatibilidad Antivirus de Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

### <a name="re-enable-microsoft-defender-antivirus-on-windows-server-2016"></a>Vuelva a habilitar Antivirus de Microsoft Defender en Windows Server 2016

Puede usar la [Utilidad de Command-Line protección contra malware](command-line-arguments-microsoft-defender-antivirus.md) para volver a habilitar Antivirus de Microsoft Defender en Windows Server 2016.

1. Como administrador local en el servidor, abra el símbolo del sistema.

2. Ejecute el siguiente comando: `MpCmdRun.exe -wdenable`

3. Reinicie el dispositivo.

### <a name="re-enable-microsoft-defender-antivirus-on-windows-server-version-1803-or-later"></a>Volver a habilitar Antivirus de Microsoft Defender en Windows Server, versión 1803 o posterior

> [!IMPORTANT]
> El siguiente procedimiento solo se aplica a los puntos de conexión o dispositivos que ejecutan las siguientes versiones de Windows:
> - Windows Server 2022
> - Windows Server 2019
> - Windows Server, versión 1803 (modo solo núcleo)

1. Como administrador local en el servidor, abra Windows PowerShell.

2. Ejecute los siguientes cmdlets de PowerShell:

   ```powershell
   # For Windows Server 2016
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Gui
   # For Windows Server 2019 and Windows Server 2022
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```

   Cuando se usa el comando DISM dentro de una secuencia de tareas que ejecuta PowerShell, se requiere la siguiente ruta de acceso a cmd.exe.
   Ejemplo:

   ```powershell
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```

3. Reinicie el dispositivo.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server

> [!TIP]
> Ahora puede ejecutar Antivirus de Microsoft Defender en modo pasivo en Windows Server 2012 R2 y 2016. Para obtener más información, vea [Opciones para instalar Microsoft Defender para punto de conexión](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages).

1. Abra el Editor del Registro y, a continuación, vaya a `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Edite (o cree) una entrada DWORD denominada **ForceDefenderPassiveMode** y especifique la siguiente configuración:

   - Establezca el valor de DWORD en **1**.

   - En **Base**, seleccione **Hexadecimal**.

> [!NOTE]
> Después de la incorporación a Defender para punto de conexión, es posible que tenga que establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server. Para validar que el modo pasivo se ha establecido según lo previsto, busque el *evento 5007* en el registro **operativo de Microsoft-Windows-Windows Defender** (ubicado en `C:\Windows\System32\winevt\Logs`) y confirme que las claves del Registro **ForceDefenderPassiveMode** o **PassiveMode** se han establecido en **0x1**.

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>¿Usa Windows Server 2012 R2 o Windows Server 2016?

Ahora puede ejecutar Antivirus de Microsoft Defender en modo pasivo en Windows Server 2012 R2 y 2016 mediante el método anterior. Para obtener más información, vea [Opciones para instalar Microsoft Defender para punto de conexión](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages).

## <a name="configure-defender-for-endpoint"></a>Configuración de Defender para punto de conexión

Este paso del proceso de migración implica la configuración de Antivirus de Microsoft Defender para los puntos de conexión. Se recomienda usar Intune; sin embargo, puede usar cualquiera de los métodos que aparecen en la tabla siguiente:

|Método|Qué hacer|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **NOTA**: Intune ahora forma parte de Microsoft Endpoint Manager.|1. Vaya al centro de [administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) e inicie sesión.<br/><br/>2. Seleccione **Dispositivos Perfiles** \> **de configuración** y, a continuación, seleccione el tipo de perfil que desea configurar. Si aún no ha creado un tipo de perfil **Restricciones** de dispositivos o si desea crear uno nuevo, consulte [Configuración de las opciones de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).<br/><br/>3. Seleccione **Propiedades** y, a continuación, seleccione **Configuración: Editar**<br/><br/>4. Expanda **Antivirus de Microsoft Defender**.<br/><br/>5. Habilite la **protección entregada en la nube**.<br/><br/>6. En la lista desplegable **Preguntar a los usuarios antes del envío de ejemplo** , seleccione **Enviar todas las muestras automáticamente**.<br/><br/>7. En la lista desplegable **Detectar aplicaciones potencialmente no deseadas** , seleccione **Habilitar** o **Auditar**.<br/><br/>8. Seleccione **Revisar y guardar** y, a continuación, elija **Guardar**. <br/><br/> **SUGERENCIA**: Para obtener más información sobre Intune perfiles de dispositivo, incluido cómo crear y configurar sus opciones, consulte [¿Qué son Microsoft Intune perfiles de dispositivo?](/intune/device-profiles).|
|Microsoft Endpoint Configuration Manager|Consulte [Creación e implementación de directivas antimalware para Endpoint Protection en Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies). <br/><br/> Al crear y configurar las directivas antimalware, asegúrese de revisar la [configuración de protección en tiempo real](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) y [habilitar el bloqueo a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md).
|Panel de control en Windows|Siga las instrucciones que se indican aquí: [Active Antivirus de Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows). (Es posible que vea *Antivirus de Windows Defender* en lugar de *Antivirus de Microsoft Defender* en algunas versiones de Windows).|
|[Administración de directivas de grupo avanzadas](/microsoft-desktop-optimization-pack/agpm/) <br/><br/> o bien <br/><br/> [Consola de administración de directivas de grupo](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)|1. Vaya a **Configuración** \> del equipo **Plantillas** \> administrativas **Windows componentes** \> **Antivirus de Microsoft Defender**.<br/><br/>2. Busque una directiva denominada **Desactivar Antivirus de Microsoft Defender**.<br/><br/>3. Elija **Editar configuración de directiva** y asegúrese de que la directiva está deshabilitada. Esta acción habilita Antivirus de Microsoft Defender. <br/>(Es posible que vea *Antivirus de Windows Defender* en lugar de *Antivirus de Microsoft Defender* en algunas versiones de Windows).|

> [!TIP]
> Puede implementar las directivas antes de que se incorporen los dispositivos de la organización.

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Agregar Microsoft Defender para punto de conexión a la lista de exclusión de la solución existente

Este paso del proceso de instalación implica agregar Defender para punto de conexión a la lista de exclusión de la solución de endpoint protection existente y cualquier otro producto de seguridad que use su organización.

> [!TIP]
> Para obtener ayuda para configurar exclusiones, consulte la documentación del proveedor de soluciones.

Las exclusiones específicas que se van a configurar dependerán de la versión de Windows los puntos de conexión o dispositivos que se ejecuten y se enumeran en la tabla siguiente.

| SO |Exclusiones |
|:--|:--|
|Windows 11 <br/><br/>Windows 10, [versión 1803](/lifecycle/announcements/windows-server-1803-end-of-servicing) o posterior (consulte [Windows 10 información de versión](/windows/release-health/release-information))<br/><br/>Windows 10, versión 1703 o 1709 con [KB4493441](https://support.microsoft.com/help/4493441) instalado <br/><br/> Windows Server 2022<br/><br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019) <br/><br/>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows Server, versión 1803](/windows-server/get-started/whats-new-in-windows-server-1803) | `C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`<br/><br/>Además, en Windows Server 2012 R2 y 2016 que ejecutan la solución moderna y unificada, se requieren las siguientes exclusiones después de actualizar el componente sense EDR mediante [KB5005292](https://support.microsoft.com/en-us/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac):<br/> <br/> `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\MsSense.exe` <br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCnCProxy.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseIR.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCE.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseSampleUploader.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCM.exe` |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**NOTA**: La supervisión de archivos temporales de host 6\45 puede ser subcarpetas numeradas diferentes.<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Agregue la solución existente a la lista de exclusión para Antivirus de Microsoft Defender

Durante este paso del proceso de instalación, agregará la solución existente a la lista de exclusión de Antivirus de Microsoft Defender. Puede elegir entre varios métodos para agregar las exclusiones a Antivirus de Microsoft Defender, como se muestra en la tabla siguiente: 

|Método|Qué hacer|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **NOTA**: Intune ahora forma parte de Microsoft Endpoint Manager.|1. Vaya al centro de [administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) e inicie sesión.<br/><br/>2. Seleccione **Dispositivos Perfiles** \> **de configuración** y, a continuación, seleccione el perfil que desea configurar.<br/><br/>3. En **Administrar**, seleccione **Propiedades**.<br/><br/>4. Seleccione **Configuración: Editar**.<br/><br/>5. Expanda **Antivirus de Microsoft Defender** y, a continuación, expanda **Exclusiones de Antivirus de Microsoft Defender**.<br/><br/>6. Especifique los archivos y carpetas, las extensiones y los procesos que se van a excluir de los exámenes de Antivirus de Microsoft Defender. Para obtener referencia, consulte [exclusiones de Antivirus de Microsoft Defender](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions).<br/><br/>7. Elija **Revisar y guardar** y, a continuación, elija **Guardar**.|
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/)|1. Con la [consola de Configuration Manager](/mem/configmgr/core/servers/manage/admin-console), vaya a **Activos y cumplimiento** \> **Endpoint Protection** \> **Directivas antimalware** y, a continuación, seleccione la directiva que desea modificar.<br/><br/>2. Especifique la configuración de exclusión de archivos y carpetas, extensiones y procesos que se van a excluir de Antivirus de Microsoft Defender exámenes.|
|[Objeto de directiva de grupo](/previous-versions/windows/desktop/Policy/group-policy-objects)|1. En el equipo de administración de directiva de grupo, abra la consola de [administración de directiva de grupo](https://technet.microsoft.com/library/cc731212.aspx), haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.<br/><br/>2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.<br/><br/>3. Expanda el árbol para **Windows componentes \> Antivirus de Microsoft Defender \> Exclusiones**. (Es posible que vea *Antivirus de Windows Defender* en lugar de *Antivirus de Microsoft Defender* en algunas versiones de Windows).<br/><br/>4. Haga doble clic en la configuración **Exclusiones de ruta de acceso** y agregue las exclusiones.<br/><br/>5. Establezca la opción **en Habilitado**.<br/><br/>6. En la sección **Opciones** , seleccione **Mostrar...**.<br/><br/>7. Especifique cada carpeta en su propia línea en la columna **Nombre del valor** . Si especifica un archivo, asegúrese de escribir una ruta de acceso completa al archivo, incluida la letra de unidad, la ruta de acceso de la carpeta, el nombre de archivo y la extensión. Escriba **0** en la columna **Valor** .<br/><br/>8. Seleccione **Aceptar**.<br/><br/>9. Haga doble clic en la configuración **Exclusiones de extensión** y agregue las exclusiones.<br/><br/>10. Establezca la opción **en Habilitado**.<br/><br/>11. En la sección **Opciones** , seleccione **Mostrar...**.<br/><br/>12. Escriba cada extensión de archivo en su propia línea en la columna **Nombre de valor** . Escriba **0** en la columna **Valor** .<br/><br/>13. Seleccione **Aceptar**.|
|Objeto de directiva de grupo local|1. En el punto de conexión o dispositivo, abra el Editor de directiva de grupo local.<br/><br/>2. Vaya a **Configuración** \> del equipo **Plantillas** \> administrativas **Windows Componentes** \> **Antivirus de Microsoft Defender** \> **Exclusiones**. (Es posible que vea *Antivirus de Windows Defender* en lugar de *Antivirus de Microsoft Defender* en algunas versiones de Windows).<br/><br/>3. Especifique la ruta de acceso y las exclusiones de proceso.|
|Clave del Registro|1. Exporte la siguiente clave del Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions`.<br/><br/>2. Importe la clave del Registro. A continuación, se indican dos ejemplos:<br/>- Ruta de acceso local: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg`<br/>- Recurso compartido de red: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg`|

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>Tenga en cuenta los siguientes puntos sobre exclusiones.

Al agregar [exclusiones a Antivirus de Microsoft Defender exámenes](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus), debe agregar exclusiones de ruta de acceso y proceso.

Tenga en cuenta los siguientes puntos:

- *Las exclusiones de ruta de acceso* excluyen archivos específicos y el acceso a esos archivos.
- *Las exclusiones de* proceso excluyen todo lo que toca un proceso, pero no excluye el propio proceso.
- Enumere las exclusiones de proceso mediante su ruta de acceso completa y no solo por su nombre. (El método de solo nombre es menos seguro).
- Si enumera cada ejecutable (.exe) como una exclusión de ruta de acceso y una exclusión de proceso, se excluye el proceso y lo que toque.

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Configuración de grupos de dispositivos, recopilaciones de dispositivos y unidades organizativas

Los grupos de dispositivos, las recopilaciones de dispositivos y las unidades organizativas permiten al equipo de seguridad administrar y asignar directivas de seguridad de forma eficaz y eficaz. En la tabla siguiente se describe cada uno de estos grupos y cómo configurarlos. Es posible que su organización no use los tres tipos de colección.

|Tipo de colección|Qué hacer|
|---|---|
|[Los grupos de dispositivos](/microsoft-365/security/defender-endpoint/machine-groups) (anteriormente denominados *grupos de máquinas*) permiten al equipo de operaciones de seguridad configurar funcionalidades de seguridad, como la investigación y la corrección automatizadas. <br/><br/> Los grupos de dispositivos también son útiles para asignar acceso a esos dispositivos para que el equipo de operaciones de seguridad pueda realizar acciones de corrección si es necesario. <br/><br/> Los grupos de dispositivos se crean en Mientras se detectó y detuvo el ataque, las alertas, como una "alerta de acceso inicial", se desencadenaron y aparecieron en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender).|1. Vaya al portal de Microsoft 365 Defender (<https://security.microsoft.com>).<br/><br/>2. En el panel de navegación de la izquierda, elija **Configuración** \> **Permisos de puntos de conexión** \> **Grupos** \> **de dispositivos**.<br/><br/>3. Elija **+ Agregar grupo de dispositivos**.<br/><br/>4. Especifique un nombre y una descripción para el grupo de dispositivos.<br/><br/>5. En la lista **Nivel de automatización**, seleccione una opción. (Se recomienda **completo: corregir las amenazas automáticamente**). Para obtener más información sobre los distintos niveles de automatización, consulte [Cómo se corrigen las amenazas](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated).<br/><br/>6. Especifique las condiciones de una regla coincidente para determinar qué dispositivos pertenecen al grupo de dispositivos. Por ejemplo, puede elegir un dominio, versiones del sistema operativo o incluso usar [etiquetas de dispositivo](/microsoft-365/security/defender-endpoint/machine-tags).<br/><br/>7. En la pestaña **Acceso de usuario** , especifique los roles que deben tener acceso a los dispositivos incluidos en el grupo de dispositivos.<br/><br/>8. Elija **Listo**.|
|[Las recopilaciones de](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) dispositivos permiten al equipo de operaciones de seguridad administrar aplicaciones, implementar la configuración de cumplimiento o instalar actualizaciones de software en los dispositivos de la organización. <br/><br/> Las colecciones de dispositivos se crean mediante [Configuration Manager](/mem/configmgr/).|Siga los pasos descritos en [Creación de una colección](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create).|
|[Las unidades organizativas](/azure/active-directory-domain-services/create-ou) permiten agrupar de forma lógica objetos como cuentas de usuario, cuentas de servicio o cuentas de equipo. <br/><br/> A continuación, puede asignar administradores a unidades organizativas específicas y aplicar la directiva de grupo para aplicar la configuración de destino. <br/><br/> Las unidades organizativas se definen en [Azure Active Directory Domain Services](/azure/active-directory-domain-services).|Siga los pasos descritos en [Creación de una unidad organizativa en un dominio administrado de Azure Active Directory Domain Services](/azure/active-directory-domain-services/create-ou).|

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena**! Ha completado la fase de configuración del [cambio a Defender para punto de conexión](switch-to-mde-overview.md#the-migration-process).

- [Pasar a la fase 3: Incorporación a Defender para punto de conexión](switch-to-mde-phase-3.md)
