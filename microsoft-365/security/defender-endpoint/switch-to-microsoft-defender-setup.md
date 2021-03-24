---
title: Cambiar a Microsoft Defender para endpoint- Setup
description: Esta es la fase 2, Configuración, para cambiar a Microsoft Defender para endpoint.
keywords: migración, protección contra amenazas avanzada de Windows Defender, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 71428db81d5cd98e02cdb7c878c1f60562653ae3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069044"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Cambiar a Microsoft Defender para endpoint - Fase 2: Configuración

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Preparar](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: Preparar](switch-to-microsoft-defender-prepare.md) |![Fase 2: Configurar](images/phase-diagrams/setup.png)<br/>Fase 2: Configurar |[![Fase 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fase 3: Incorporación](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*¡Estás aquí!* | |

**Bienvenido a la fase de configuración de [cambiar a Microsoft Defender para endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. Esta fase incluye los siguientes pasos:
1. [Habilite Antivirus de Microsoft Defender y confirme que está en modo pasivo](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).
2. [Obtener actualizaciones para Antivirus de Microsoft Defender](#get-updates-for-microsoft-defender-antivirus).
3. [Agregue Microsoft Defender para endpoint a la lista de exclusión de la solución de extremo existente.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)
4. [Agregue la solución existente a la lista de exclusión de Antivirus de Microsoft Defender](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus).
5. [Agregue la solución existente a la lista de exclusión de Microsoft Defender para endpoint](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint).
6. [Configure los grupos de dispositivos, las colecciones de dispositivos y las unidades organizativas.](#set-up-your-device-groups-device-collections-and-organizational-units)
7. [Configurar directivas antimalware y protección en tiempo real](#configure-antimalware-policies-and-real-time-protection).

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>Habilitar Antivirus de Microsoft Defender y confirmar que está en modo pasivo

En determinadas versiones de Windows, como Windows Server, es posible que antivirus de Microsoft Defender se haya desinstalado o deshabilitado cuando se instaló la solución de McAfee. Esto se debe a que Antivirus de Microsoft Defender no entra en modo pasivo o deshabilitado al instalar un producto antivirus de terceros, como McAfee. (Para obtener más información sobre esto, vea [Compatibilidad de Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)).)

Este paso del proceso de migración incluye las siguientes tareas:
- [Establecer DisableAntiSpyware en false en Windows Server](#set-disableantispyware-to-false-on-windows-server)
- [Reinstalar Antivirus de Microsoft Defender en Windows Server;](#reinstall-microsoft-defender-antivirus-on-windows-server)
- [Establecer el Antivirus de Microsoft Defender en modo pasivo en Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [Habilitar El Antivirus de Microsoft Defender en los dispositivos cliente de Windows;](#enable-microsoft-defender-antivirus-on-your-windows-client-devices) y
- [Confirmando que Antivirus de Microsoft Defender está establecido en modo pasivo](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode).  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Establecer DisableAntiSpyware en false en Windows Server

La clave del Registro [DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) se usó en el pasado para deshabilitar Antivirus de Microsoft Defender e implementar otro producto antivirus, como McAfee. En general, no debe tener esta clave del Registro en los dispositivos y puntos de conexión de Windows; sin embargo, si ha configurado, aquí le indicamos cómo establecer `DisableAntiSpyware` su valor en false:

1. En el dispositivo Windows Server, abra el Editor del Registro.
2. Vaya a `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.
3. En esa carpeta, busque una entrada DWORD denominada **DisableAntiSpyware**.
   - Si no ve esa entrada, está todo establecido.
   - Si ves **DisableAntiSpyware,** continúa con el paso 4.
4. Haga clic con el botón secundario en el DWORD DisableAntiSpyware y, a continuación, elija **Modificar**.
5. Establezca el valor en `0` . (Esto establece el valor de la clave del Registro en *false*.)

> [!TIP]
> Para obtener más información acerca de esta clave del Registro, [vea DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware).

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Reinstalar Antivirus de Microsoft Defender en Windows Server

> [!NOTE]
> El siguiente procedimiento solo se aplica a los puntos de conexión o dispositivos que ejecutan las siguientes versiones de Windows:
> - Windows Server 2019
> - Windows Server, versión 1803 (modo de solo núcleo)
> - Windows Server 2016

1. Como administrador local en el punto de conexión o dispositivo, abra Windows PowerShell.
2. Ejecute los siguientes cmdlets de PowerShell: <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
   > [!NOTE]
   > Cuando se usa el comando DISM en una secuencia de tareas que ejecuta PS, se requiere la siguiente ruta de cmd.exe.
   > Ejemplo:<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>
3. Para comprobar que antivirus de Microsoft Defender se está ejecutando, use el siguiente cmdlet de PowerShell: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>¿Estás usando Windows Server 2016?

Si usa Windows Server 2016 y tiene problemas para habilitar Antivirus de Microsoft Defender, use el siguiente cmdlet de PowerShell:

`mpcmdrun -wdenable`

> [!TIP]
> ¿Aún necesita ayuda? Consulta [Antivirus de Microsoft Defender en Windows Server](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Establecer antivirus de Microsoft Defender en modo pasivo en Windows Server

Dado que su organización sigue usando la solución de protección de puntos de conexión existente, debe establecer Antivirus de Microsoft Defender en modo pasivo. De este modo, la solución existente y el Antivirus de Microsoft Defender pueden ejecutarse en paralelo hasta que haya terminado de incorporarse a Microsoft Defender para endpoint.

1. Abra el Editor del Registro y, a continuación, vaya a <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.
2. Edite (o cree) una entrada DWORD denominada **ForceDefenderPassiveMode** y especifique la siguiente configuración:
   - Establezca el valor de DWORD en **1**.
   - En **Base**, seleccione **Hexadecimal**.

> [!NOTE]
> Puede usar otros métodos para establecer la clave del Registro, como los siguientes:
>- [Preferencia de directiva de grupo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Herramienta Objeto de directiva de grupo local](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Un paquete en Configuration Manager](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>Habilitar Antivirus de Microsoft Defender en los dispositivos cliente de Windows

Dado que su organización ha estado usando una solución antivirus que no es de Microsoft, es más probable que Antivirus de Microsoft Defender esté deshabilitado en los dispositivos Windows de la organización. Este paso del proceso de migración implica habilitar Antivirus de Microsoft Defender. 

Para habilitar Antivirus de Microsoft Defender, se recomienda usar Intune. Sin embargo, puede cualquiera de los métodos que se enumeran en la tabla siguiente:

|Método  |Qué hacer  |
|---------|---------|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**NOTA:** Intune ahora es Microsoft Endpoint Manager. |1. Vaya al Centro de administración [de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) e inicie sesión.<br/>2. Seleccione **Perfiles**  >  **de configuración de dispositivos** y, a continuación, seleccione el tipo de perfil que desea configurar. Si aún no has creado un tipo de perfil de **restricciones** de dispositivo o quieres crear uno nuevo, consulta Configurar la configuración de restricción de [dispositivos en Microsoft Intune](https://docs.microsoft.com/intune/device-restrictions-configure).<br/>3. Seleccione **Propiedades** y, a continuación, **seleccione Configuración: Editar**.<br/>4. Expanda **Antivirus de Microsoft Defender**. <br/>5. Habilitar la **protección entregada en la nube.**<br/>6. En la lista desplegable Preguntar a **los usuarios antes del** envío de ejemplo, seleccione Enviar todos los ejemplos **automáticamente.**<br/>7. En el desplegable **Detectar aplicaciones potencialmente no deseadas,** seleccione **Habilitar** o **Auditar**.<br/>8. Seleccione **Revisar + guardar** y, a continuación, elija **Guardar**.<br/>**SUGERENCIA:** Para obtener más información acerca de los perfiles de dispositivo de Intune, incluido cómo crear y configurar sus opciones, vea ¿Qué son los perfiles de dispositivo de [Microsoft Intune?](https://docs.microsoft.com/intune/device-profiles).|
|Panel de control en Windows     |Siga las instrucciones aquí: [Activar Antivirus de Microsoft Defender](https://docs.microsoft.com/mem/intune/user-help/turn-on-defender-windows). <br/>**NOTA:** Es posible que *veas Windows Defender antivirus* en lugar de Antivirus de *Microsoft Defender* en algunas versiones de Windows.        |
|[Administración de directivas de grupo avanzadas](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) <br/>o<br/>[Consola de administración de directivas de grupo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Vaya a `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <br/>2. Busque una directiva denominada **Desactivar Antivirus de Microsoft Defender**.<br/>3. Elija **Editar configuración de directiva** y asegúrese de que la directiva está deshabilitada. Esto habilita Antivirus de Microsoft Defender. <br/>**NOTA:** Es posible que *veas Windows Defender antivirus* en lugar de Antivirus de *Microsoft Defender* en algunas versiones de Windows. |

### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Confirmar que Antivirus de Microsoft Defender está en modo pasivo

Antivirus de Microsoft Defender puede ejecutarse junto con la solución de protección de puntos de conexión existente si establece Antivirus de Microsoft Defender en modo pasivo. Puede usar el símbolo del sistema o PowerShell para realizar esta tarea, como se describe en la tabla siguiente:

|Método  |Qué hacer  |
|---------|---------|
|Símbolo del sistema     |1. En un dispositivo Windows, abra símbolo del sistema como administrador. <br/>2. Escriba `sc query windefend` y, a continuación, presione ENTRAR.<br/>3. Revise los resultados para confirmar que antivirus de Microsoft Defender se está ejecutando en modo pasivo.         |
|PowerShell     |1. En un dispositivo Windows, abra Windows PowerShell como administrador.<br/>2. Ejecute el cmdlet [Get-MpComputerStatus.](https://docs.microsoft.com/powershell/module/defender/Get-MpComputerStatus) <br/>3. En la lista de resultados, busque **AMRunningMode: Passive Mode** o **AMRunningMode: SxS Passive Mode**.          |

> [!NOTE]
> Es posible que *veas Windows Defender antivirus* en lugar de *Antivirus de Microsoft Defender* en algunas versiones de Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Obtener actualizaciones para Antivirus de Microsoft Defender

Mantener el Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de malware y ataques, incluso si Antivirus de Microsoft Defender se ejecuta en modo [pasivo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Hay dos tipos de actualizaciones relacionadas con la actualización del Antivirus de Microsoft Defender:
- Actualizaciones de inteligencia de seguridad
- Actualizaciones de productos

Para obtener las actualizaciones, siga las instrucciones de [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Agregar Microsoft Defender para endpoint a la lista de exclusión de la solución existente

Este paso del proceso de configuración implica agregar Microsoft Defender para Endpoint a la lista de exclusión de la solución de protección de puntos de conexión existente y cualquier otro producto de seguridad que su organización esté usando. 

> [!TIP]
> Para obtener ayuda para configurar exclusiones, consulte la documentación del proveedor de soluciones.

Las exclusiones específicas que se van a configurar dependen de la versión de Windows en la que se ejecuten los puntos de conexión o dispositivos y se enumeran en la tabla siguiente:

|Sistema operativo |Exclusiones |
|--|--|
|- Windows 10, [versión 1803](https://docs.microsoft.com/windows/release-health/status-windows-10-1803) o posterior (consulta Información de [la versión de Windows 10](https://docs.microsoft.com/windows/release-health/release-information))<br/>- Windows 10, versión 1703 [o 1709](https://docs.microsoft.com/windows/release-health/status-windows-10-1709) con [KB4493441](https://support.microsoft.com/help/4493441) instalado <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, versión 1803](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**NOTA:** Donde los archivos temporales de host de supervisión 6\45 pueden ser subcarpetas numeradas diferentes.<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Agregar la solución existente a la lista de exclusión de Antivirus de Microsoft Defender

Durante este paso del proceso de configuración, agregará la solución existente a la lista de exclusión de Antivirus de Microsoft Defender. 

Al agregar exclusiones a exámenes de [Antivirus de Microsoft Defender,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)debe agregar exclusiones de ruta de acceso y proceso. Tenga en cuenta los siguientes puntos:
- Las exclusiones de ruta de acceso excluyen archivos específicos y cualquier acceso a esos archivos.
- Las exclusiones de procesos excluyen lo que toca un proceso, pero no excluyen el proceso en sí.
- Si enumera cada archivo ejecutable (.exe) como una exclusión de ruta de acceso y una exclusión de proceso, se excluirá el proceso y lo que toque.
- Enumera las exclusiones de proceso con su ruta de acceso completa y no solo por su nombre. (El método de solo nombre es menos seguro).

Puedes elegir entre varios métodos para agregar las exclusiones al Antivirus de Microsoft Defender, como se muestra en la tabla siguiente:

|Método | Qué hacer|
|--|--|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**NOTA:** Intune ahora es Microsoft Endpoint Manager. |1. Vaya al Centro de administración [de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) e inicie sesión.<br/>2. Seleccione **Perfiles**  >  **de configuración de dispositivos** y, a continuación, seleccione el perfil que desea configurar.<br/>3. En **Administrar**, seleccione **Propiedades**. <br/>4. Seleccione **Configuración: Editar**.<br/>5. Expanda **Antivirus de Microsoft Defender** y, a continuación, expanda **Exclusiones antivirus de Microsoft Defender**.<br/>6. Especifique los archivos y carpetas, las extensiones y los procesos que se excluirán de los exámenes del Antivirus de Microsoft Defender. Para obtener referencia, consulte [Exclusiones de Antivirus de Microsoft Defender](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions).<br/>7. Elija **Revisar + guardar** y, a continuación, elija **Guardar**.  |
|[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/) |1. Con la consola [de Configuration Manager,](https://docs.microsoft.com/mem/configmgr/core/servers/manage/admin-console)vaya a **Assets and Compliance** Endpoint Protection Antimalware Policies y, a continuación, seleccione la  >    >  directiva que desea modificar. <br/>2. Especifique la configuración de exclusión de archivos y carpetas, extensiones y procesos que se excluirán de los exámenes del Antivirus de Microsoft Defender. |
|[Objeto de directiva de grupo](https://docs.microsoft.com/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.<br/>2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo** y haga clic en **Plantillas administrativas.**<br/>3. Expande el árbol a componentes **de Windows > Antivirus de Microsoft Defender > exclusiones.**<br/>**NOTA:** Es posible que *veas Windows Defender antivirus* en lugar de Antivirus de *Microsoft Defender* en algunas versiones de Windows.<br/>4. Haga doble clic en la configuración **Exclusiones de ruta de** acceso y agregue las exclusiones.<br/>- Establezca la opción en **Habilitado**.<br/>- En la **sección Opciones,** haga clic **en Mostrar...**.<br/>- Especifique cada carpeta en su propia línea en la **columna Nombre de** valor.<br/>- Si especifica un archivo, asegúrese de escribir una ruta de acceso completa al archivo, incluida la letra de unidad, la ruta de acceso de carpeta, el nombre de archivo y la extensión. Escriba **0** en la **columna** Valor.<br/>5. Haga clic en **Aceptar**.<br/>6. Haga doble clic en la configuración **Exclusiones de extensión** y agregue las exclusiones.<br/>- Establezca la opción en **Habilitado**.<br/>- En la **sección Opciones,** haga clic **en Mostrar...**.<br/>- Escriba cada extensión de archivo en su propia línea en la **columna Nombre de** valor.  Escriba **0** en la **columna** Valor.<br/>7. Haga clic en **Aceptar**. |
|Objeto de directiva de grupo local |1. En el punto de conexión o el dispositivo, abra el Editor de directivas de grupo local. <br/>2. Vaya a **Configuración del equipo** Plantillas administrativas Componentes de Windows  >    >  **Exclusiones** del antivirus de  >  **Microsoft Defender**  >  . <br/>**NOTA:** Es posible que *veas Windows Defender antivirus* en lugar de Antivirus de *Microsoft Defender* en algunas versiones de Windows.<br/>3. Especifique la ruta de acceso y las exclusiones de procesos. |
|Clave del Registro |1. Exporte la siguiente clave del Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/>2. Importe la clave del Registro. A continuación, se indican dos ejemplos:<br/>- Ruta de acceso local: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Recurso compartido de red: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Agregar la solución existente a la lista de exclusión de Microsoft Defender para endpoint

Para agregar exclusiones a Microsoft Defender para endpoint, se crean [indicadores](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files).

1. Vaya al Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e inicie sesión.
2. En el panel de navegación, elija **Settings**  >  **Rules**  >  **Indicators**.
3.  En la **pestaña Hashes de** archivo, elija **Agregar indicador**.
4. En la **pestaña Indicador,** especifique la siguiente configuración:
   - Hash de archivo (¿Necesita ayuda? Vea [Find a file hash using CMPivot](#find-a-file-hash-using-cmpivot) en este artículo).
   - En **Expira en (UTC),** elija **Nunca**.
5. En la **pestaña** Acción, especifique la siguiente configuración:
   - **Acción de respuesta:** **Permitir**
   - Título y descripción
6. En la **pestaña Ámbito,** en **Grupos de dispositivos,** seleccione Todos los **dispositivos de mi ámbito** o Seleccionar de la **lista**.
7. En la **pestaña Resumen,** revise la configuración y, a continuación, haga clic **en Guardar**.

### <a name="find-a-file-hash-using-cmpivot"></a>Buscar un hash de archivo con CMPivot

CMPivot es una utilidad en la consola para Configuration Manager. CMPivot proporciona acceso al estado en tiempo real de los dispositivos en su entorno. Ejecuta inmediatamente una consulta en todos los dispositivos conectados actualmente en la colección de destino y devuelve los resultados. Para obtener más información, vea [Introducción a CMPivot](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot-overview).

Para usar CMPivot para obtener el hash de archivo, siga estos pasos:

1. Revise los [requisitos previos](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#prerequisites).
2. [Inicie CMPivot](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot). 
3. Conectarse a Configuration Manager ( `SCCM_ServerName.DomainName.com` ).
4. Seleccione la **pestaña** Consulta.
5. En la **lista Colección de** dispositivos, elija Todos los sistemas **(predeterminado).**
6. En el cuadro de consulta, escriba la siguiente consulta:<br/>

   ```kusto
   File(c:\\windows\\notepad.exe)
   | project Hash
   ```
   
   > [!NOTE]
   > En la consulta anterior, reemplace *notepad.exe* por el nombre del proceso de producto de seguridad de terceros. 

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Configurar grupos de dispositivos, colecciones de dispositivos y unidades organizativas

| Tipo de colección | Qué hacer |
|--|--|
|[Los grupos de dispositivos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) (anteriormente denominados grupos de máquinas) permiten al equipo de operaciones de seguridad configurar funciones de seguridad, como la investigación automatizada y la corrección.<br/> Los grupos de dispositivos también son útiles para asignar acceso a esos dispositivos para que el equipo de operaciones de seguridad pueda realizar acciones de corrección si es necesario. <br/>Los grupos de dispositivos se crean en el Centro de seguridad de Microsoft Defender. |1. Vaya al Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/>2. En el panel de navegación de la izquierda, elija **Configuración** Permisos Grupos de  >    >  **dispositivos**.  <br/>3. Elija **+ Agregar grupo de dispositivos**.<br/>4. Especifique un nombre y una descripción para el grupo de dispositivos.<br/>5. En la **lista Nivel de automatización,** seleccione una opción. (Se recomienda **Full: corregir las amenazas automáticamente).)** Para obtener más información sobre los distintos niveles de automatización, vea [How threats are remediated](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated).<br/>6. Especifique las condiciones de una regla de coincidencia para determinar qué dispositivos pertenecen al grupo de dispositivos. Por ejemplo, puedes elegir un dominio, versiones del sistema operativo o incluso usar etiquetas [de dispositivo.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags) <br/>7. En la **pestaña Acceso de** usuario, especifique los roles que deben tener acceso a los dispositivos que se incluyen en el grupo de dispositivos. <br/>8. Elija **Listo**. |
|[Las colecciones de dispositivos](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/introduction-to-collections) permiten al equipo de operaciones de seguridad administrar aplicaciones, implementar la configuración de cumplimiento o instalar actualizaciones de software en los dispositivos de la organización. <br/>Las colecciones de dispositivos se crean mediante [Configuration Manager](https://docs.microsoft.com/mem/configmgr/). |Siga los pasos de [Crear una colección](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[Las unidades](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) organizativas permiten agrupar lógicamente objetos como cuentas de usuario, cuentas de servicio o cuentas de equipo. A continuación, puede asignar administradores a unidades organizativas específicas y aplicar una directiva de grupo para aplicar las opciones de configuración de destino.<br/> Las unidades organizativas se definen [en Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services). | Siga los pasos de [Crear una unidad organizativa en un dominio](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou)administrado de Azure Active Directory Domain Services . |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Configurar directivas antimalware y protección en tiempo real

Con Configuration Manager y las colecciones de dispositivos, configure las directivas de antimalware.
- Vea [Crear e implementar directivas antimalware para Endpoint Protection en Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies).
- Mientras crea y configura las directivas antimalware, asegúrese de revisar la configuración de protección en tiempo [real](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) y [habilitar el bloqueo a primera vista](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus).

> [!TIP]
> Puedes implementar las directivas antes de que los dispositivos de la organización se incorpore.

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena!** Ha completado la fase de configuración de [cambiar a Microsoft Defender para Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)!

- [Continúe con la fase 3: Incorporación a Microsoft Defender para el extremo](switch-to-microsoft-defender-onboard.md)
