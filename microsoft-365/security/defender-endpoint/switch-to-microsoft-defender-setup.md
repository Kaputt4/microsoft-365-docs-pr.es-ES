---
title: Cambiar a Microsoft Defender para endpoint- Setup
description: Realice el cambio a Defender para endpoint. Revise el proceso de instalación, que incluye la instalación de Antivirus de Microsoft Defender.
keywords: migración, Microsoft Defender para endpoint, antivirus, modo pasivo, proceso de configuración
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
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom: migrationguides
ms.date: 08/16/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 0ec7bf5f279cef713e81b4051d3a756aa0a3c3bf
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58563539"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Cambiar a Microsoft Defender para endpoint - Fase 2: Configuración

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Preparar.](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: Preparación](switch-to-microsoft-defender-prepare.md) |![Fase 2: Configuración](images/phase-diagrams/setup.png)<br/>Fase 2: Configuración |[![Fase 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fase 3: Incorporación](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*¡Estás aquí!* | |

**Bienvenido a la fase de configuración de [cambiar a Defender para endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. Esta fase incluye los siguientes pasos:

1. [Vuelva a instalar o Antivirus de Microsoft Defender en los puntos de conexión](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).
2. [Configurar Defender para endpoint](#configure-defender-for-endpoint).
3. [Agregar Defender para endpoint a la lista de exclusión de la solución existente.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)
4. [Agregue la solución existente a la lista de exclusión de Antivirus de Microsoft Defender](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus).
5. [Configure los grupos de dispositivos, las colecciones de dispositivos y las unidades organizativas.](#set-up-your-device-groups-device-collections-and-organizational-units)

## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>Reinstalar o habilitar Antivirus de Microsoft Defender en los puntos de conexión

En algunas versiones de Windows, Antivirus de Microsoft Defender se desinstale o deshabilitó probablemente cuando se instaló la solución antivirus o antimalware que no es de Microsoft. Cuando los puntos de conexión Windows se incorpore a Defender for Endpoint, Antivirus de Microsoft Defender puede ejecutarse en modo pasivo junto con una solución antivirus que no sea de Microsoft. Para obtener más información, vea [Antivirus protection with Defender for Endpoint](microsoft-defender-antivirus-compatibility.md#antivirus-protection-with-defender-for-endpoint).

Al cambiar a Defender for Endpoint, es posible que deba realizar ciertos pasos para reinstalar o habilitar Antivirus de Microsoft Defender. En la tabla siguiente se describe qué hacer en los Windows clientes y servidores.


| Tipo de extremo  | Qué hacer  |
|---------|---------|
| Windows clientes (como puntos de conexión que ejecutan Windows 10)     | En general, no es necesario realizar ninguna acción para los Windows (a menos que Antivirus de Microsoft Defender se haya desinstalado). Este es el motivo: <br/><br/>Antivirus de Microsoft Defender debe instalarse, pero lo más probable es que esté deshabilitado en este punto del proceso de migración.<br/><br/> Cuando se instala una solución antivirus o antimalware que no es de Microsoft y los clientes aún no están incorporados a Defender for Endpoint, Antivirus de Microsoft Defender se deshabilita automáticamente. <br/><br/>Más adelante, cuando los puntos de conexión de cliente se incorporen a Defender for Endpoint, si esos puntos de conexión ejecutan una solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender pasa al modo pasivo. <br/><br/>Si se desinstala la solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender pasa al modo activo automáticamente.  |
| Windows servidores     | En Windows server, deberá volver a instalar el Antivirus de Microsoft Defender y establecerlo en modo pasivo manualmente. Este es el motivo: <br/><br/>En Windows, cuando se instala un antivirus o antimalware que no es de Microsoft, Antivirus de Microsoft Defender puede ejecutarse junto con la solución antivirus que no es de Microsoft. En esos casos, Antivirus de Microsoft Defender se deshabilita o desinstala manualmente. <br/><br/>Para reinstalar o habilitar Antivirus de Microsoft Defender en Windows server, realice las siguientes tareas: <br/><br/>- [Establecer DisableAntiSpyware en false en Windows Server](#set-disableantispyware-to-false-on-windows-server) (solo si es necesario)<br/>- [Reinstalar Antivirus de Microsoft Defender en Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server)<br/>- [Establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)       |


> [!TIP]
> Para obtener más información sobre Antivirus de Microsoft Defender con protección antivirus que no es de Microsoft, [vea Antivirus de Microsoft Defender compatibilidad](microsoft-defender-antivirus-compatibility.md).

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Establecer DisableAntiSpyware en false en Windows Server

La clave del Registro [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) se usó en el pasado para deshabilitar Antivirus de Microsoft Defender e implementar otro producto antivirus, como McAfee, Symantec u otros. **En general, no debe tener esta clave del Registro en los** Windows dispositivos y puntos de conexión ; sin embargo, *si ha* configurado, aquí le indicamos cómo establecer su valor en `DisableAntiSpyware` false:

1. En el dispositivo Windows server, abra el Editor del Registro.

2. Vaya a `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. En esa carpeta, busque una entrada DWORD denominada **DisableAntiSpyware**.
   - Si no ve esa entrada, está todo establecido.
   - Si ves **DisableAntiSpyware,** continúa con el paso 4.

4. Haga clic con el botón secundario en el DWORD DisableAntiSpyware y, a continuación, elija **Modificar**.

5. Establezca el valor en `0` . (Esta acción establece el valor de la clave del Registro en *false*.)

> [!TIP]
> Para obtener más información acerca de esta clave del Registro, [vea DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware).

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Reinstalar Antivirus de Microsoft Defender en Windows Server

> [!IMPORTANT]
> El siguiente procedimiento solo se aplica a los puntos de conexión o dispositivos que ejecutan las siguientes versiones de Windows:
> - Windows Server 2019
> - Windows Servidor, versión 1803 (modo de solo núcleo)
> - Windows Server 2016 (vea la siguiente sección, [¿está usando Windows Server 2016?](#are-you-using-windows-server-2016))

1. Como administrador local en el punto de conexión o dispositivo, abra Windows PowerShell.

2. Ejecute los siguientes cmdlets de PowerShell: <br/>   

   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
   Cuando se usa el comando DISM dentro de una secuencia de tareas que ejecuta PowerShell, se requiere la siguiente ruta de cmd.exe.
   Ejemplo:<br/>
   
   `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
   `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server

1. Abra el Editor del Registro y, a continuación, vaya a <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Edite (o cree) una entrada DWORD denominada **ForceDefenderPassiveMode** y especifique la siguiente configuración:

   - Establezca el valor de DWORD en **1**.
   - En **Base**, seleccione **Hexadecimal**.

> [!NOTE]
> Después de incorporarse a Defender for Endpoint, es posible que deba establecer Antivirus de Microsoft Defender modo pasivo en Windows Server. Para validar que el modo pasivo se estableció como se esperaba, busque el evento *5007* en el registro operativo de **Microsoft-Windows-Windows Defender** (ubicado en ), y confirme que las claves del Registro `C:\Windows\System32\winevt\Logs` **ForceDefenderPassiveMode** o **PassiveMode** se han establecido en **0x1**.

### <a name="are-you-using-windows-server-2016"></a>¿Estás usando Windows Server 2016?

Actualmente, no puede ejecutar Antivirus de Microsoft Defender en modo pasivo en Windows Server 2016. Desinstale la solución antivirus o antimalware que no es de Microsoft e instale o habilite Antivirus de Microsoft Defender. Si tiene problemas para habilitar Antivirus de Microsoft Defender en Windows Server 2016, siga estos pasos:

1. En el dispositivo, abra PowerShell como administrador.

2. Escriba el siguiente cmdlet de PowerShell: `mpcmdrun -wdenable` .

> [!TIP]
> Para más información, consulte los siguientes artículos:
> - [Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md)
> - [Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad](microsoft-defender-antivirus-compatibility.md)

### <a name="confirm-that-microsoft-defender-antivirus-is-enabled"></a>Confirme que Antivirus de Microsoft Defender está habilitado

Puede usar uno de varios métodos para confirmar el estado de Antivirus de Microsoft Defender, tal como se describe en la tabla siguiente:

| Método | Procedure |
|:---|:---|
| Seguridad de Windows app | 1. En un Windows, abra la aplicación Seguridad de Windows usuario. <br/>2. Seleccione **Virus & protección contra amenazas**.<br/>3. **¿Quién está protegiendo?** seleccione **Administrar proveedores**. <br/>4. En la página **Proveedores de** seguridad, en **Antivirus,** debería ver Antivirus de Microsoft Defender **está activado**. |
| Administrador de tareas | 1. En un dispositivo Windows, abra la aplicación Administrador de tareas. <br/>2. Seleccione la **pestaña** Detalles.<br/>3. Busque **MsMpEng.exe** en la lista. |
| Windows PowerShell <br/> (Para confirmar que Antivirus de Microsoft Defender se está ejecutando) | 1. En un dispositivo Windows, abra Windows PowerShell.<br/>2. Ejecute el siguiente cmdlet de PowerShell: `Get-Process` .<br/>3. Revise los resultados. Debería ver **MsMpEng.exe** si Antivirus de Microsoft Defender está habilitado. |
| Windows PowerShell <br/> (Para confirmar que la protección antivirus está en su lugar) | Puede usar el [cmdlet de PowerShell Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).<br/>1. En un dispositivo Windows, abra Windows PowerShell.<br/>2. Ejecute el siguiente cmdlet de PowerShell: `Get-MpComputerStatus | select AMRunningMode` .<br/>3. Revise los resultados. Debería ver **Normal** o **Pasivo** si Antivirus de Microsoft Defender está habilitado en el punto de conexión. |

> [!TIP]
> [Obtenga más información sobre Antivirus de Microsoft Defender estados](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states).

## <a name="configure-defender-for-endpoint"></a>Configurar Defender para el extremo

Este paso del proceso de migración implica la configuración de Antivirus de Microsoft Defender para los puntos de conexión. Se recomienda usar Intune; sin embargo, puede cualquiera de los métodos que se enumeran en la tabla siguiente:

|Método  |Qué hacer  |
|---------|---------|
| [Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**NOTA:** Intune ahora forma parte de Microsoft Endpoint Manager. | 1. Vaya al Centro [Microsoft Endpoint Manager administración e](https://go.microsoft.com/fwlink/?linkid=2109431) inicie sesión.<br/> 2. Seleccione **Perfiles**  >  **de configuración de dispositivos** y, a continuación, seleccione el tipo de perfil que desea configurar. Si aún no has creado un tipo de perfil de **restricciones** de dispositivo o quieres crear uno nuevo, consulta Configurar la configuración de restricción de dispositivo en [Microsoft Intune](/intune/device-restrictions-configure).<br/> 3. Seleccione **Propiedades** y, a continuación, **seleccione Configuración: Editar**.<br/>4. Expanda **Antivirus de Microsoft Defender**. <br/>5. Habilitar la **protección entregada en la nube.**<br/>6. En la lista desplegable Preguntar a **los usuarios antes del** envío de ejemplo, seleccione Enviar todos los ejemplos **automáticamente.**<br/> 7. En el desplegable **Detectar aplicaciones potencialmente no deseadas,** seleccione **Habilitar** o **Auditar**.<br/>8. Seleccione **Revisar + guardar** y, a continuación, elija **Guardar**.<br/><br/>**SUGERENCIA:** Para obtener más información acerca de los perfiles de dispositivo de Intune, incluido cómo crear y configurar sus opciones, consulte ¿Qué Microsoft Intune [perfiles de dispositivo?](/intune/device-profiles).|
| Microsoft Endpoint Configuration Manager    | Vea [Create and deploy antimalware policies for Endpoint Protection in Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies). <br/><br/> Al crear y configurar las directivas de antimalware, asegúrese de revisar la configuración de protección en tiempo [real](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) y [habilitar el bloqueo a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md).
| Panel de control en Windows     |Siga las instrucciones aquí: [Activar Antivirus de Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows). (Es posible que *vea Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows).        |
| [Administración de directivas de grupo avanzadas](/microsoft-desktop-optimization-pack/agpm/) <br/>o<br/>[Consola de administración de directivas de grupo](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. Vaya a **Configuración del** equipo Plantillas administrativas Windows  >    >  **componentes**  >  **Antivirus de Microsoft Defender**. <br/> 2. Busque una directiva denominada **Desactivar Antivirus de Microsoft Defender**.<br/> 3. Elija **Editar configuración de directiva** y asegúrese de que la directiva está deshabilitada. Esta acción permite Antivirus de Microsoft Defender. (Es posible que *vea Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows). |

> [!TIP]
> Puede implementar las directivas antes de que los dispositivos de la organización se incorpore.
  
## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Agregar Microsoft Defender para endpoint a la lista de exclusión de la solución existente

Este paso del proceso de configuración implica agregar Defender for Endpoint a la lista de exclusión de la solución de protección de puntos de conexión existente y cualquier otro producto de seguridad que su organización esté usando. 

> [!TIP]
> Para obtener ayuda para configurar exclusiones, consulte la documentación del proveedor de soluciones.

Las exclusiones específicas que se van a configurar dependerán de la versión de Windows los puntos de conexión o dispositivos que se ejecuten y se enumeran en la tabla siguiente:

|SO |Exclusiones |
|--|--|
|Windows 10, [versión 1803](/windows/release-health/status-windows-10-1803) o posterior (vea [Windows 10 de la versión )](/windows/release-health/release-information)<br/>Windows 10, versión 1703 o 1709 con [KB4493441](https://support.microsoft.com/help/4493441) instalado <br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>[Windows Servidor, versión 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`  |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**NOTA:** La supervisión de archivos temporales de host 6\45 puede ser subcarpetas numeradas diferentes. <br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Agregue la solución existente a la lista de exclusión para Antivirus de Microsoft Defender

Durante este paso del proceso de instalación, se agrega la solución existente a la Antivirus de Microsoft Defender de exclusión. Puede elegir entre varios métodos para agregar las exclusiones a Antivirus de Microsoft Defender, como se muestra en la tabla siguiente:

|Método | Qué hacer|
|:---|:---|
| [Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**NOTA:** Intune ahora forma parte de Microsoft Endpoint Manager. | 1. Vaya al Centro [Microsoft Endpoint Manager administración e](https://go.microsoft.com/fwlink/?linkid=2109431) inicie sesión.<br/> 2. Seleccione **Perfiles**  >  **de configuración de dispositivos** y, a continuación, seleccione el perfil que desea configurar.<br/>3. En **Administrar**, seleccione **Propiedades**.<br/> 4. Seleccione **Configuración: Editar**.<br/> 5. Expanda **Antivirus de Microsoft Defender** y, a continuación, expanda **Antivirus de Microsoft Defender exclusiones**.<br/> 6. Especifique los archivos y carpetas, las extensiones y los procesos que se excluirán de Antivirus de Microsoft Defender análisis. Para obtener referencia, [vea Antivirus de Microsoft Defender exclusiones](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions).<br/> 7. Elija **Revisar + guardar** y, a continuación, elija **Guardar**.  |
| [Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. Con la consola [de Configuration Manager,](/mem/configmgr/core/servers/manage/admin-console)vaya a **Assets and Compliance** Endpoint Protection Antimalware Policies y, a continuación, seleccione la directiva  >    >  que desea modificar. <br/>2. Especifique la configuración de exclusión de archivos y carpetas, extensiones y procesos que se excluirán de Antivirus de Microsoft Defender análisis. |
| [Objeto de directiva de grupo](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.<br/> 2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo** y seleccione **Plantillas administrativas.**<br/> 3. Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > exclusiones**. (Es posible que *vea Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows).<br/>4. Haga doble clic en la configuración **Exclusiones de ruta de** acceso y agregue las exclusiones.<br/>- Establezca la opción en **Habilitado**.<br/>- En la **sección Opciones,** seleccione **Mostrar...**.<br/>- Especifique cada carpeta en su propia línea en la **columna Nombre de** valor.<br/>- Si especifica un archivo, asegúrese de escribir una ruta de acceso completa al archivo, incluida la letra de unidad, la ruta de acceso de carpeta, el nombre de archivo y la extensión. Escriba **0** en la **columna** Valor.<br/>5. Seleccione **Aceptar**.<br/>6. Haga doble clic en la configuración **Exclusiones de extensión** y agregue las exclusiones.<br/>- Establezca la opción en **Habilitado**.<br/>- En la **sección Opciones,** seleccione **Mostrar...**.<br/>- Escriba cada extensión de archivo en su propia línea en la **columna Nombre de** valor.  Escriba **0** en la **columna** Valor.<br/>7. Seleccione **Aceptar**. |
| Objeto de directiva de grupo local |1. En el punto de conexión o el dispositivo, abra el Editor de directivas de grupo local. <br/>2. Vaya a **Configuración del** equipo Plantillas administrativas Windows  >    >  **componentes**  >  **Antivirus de Microsoft Defender**  >  **exclusiones**. (Es posible que *vea Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows).<br/>3. Especifique la ruta de acceso y las exclusiones de procesos. |
| Clave del Registro |1. Exporte la siguiente clave del Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/>2. Importe la clave del Registro. A continuación, se indican dos ejemplos:<br/>- Ruta de acceso local: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Recurso compartido de red: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>Tenga en cuenta los siguientes puntos acerca de las exclusiones

Al agregar [exclusiones a los Antivirus de Microsoft Defender,](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)debe agregar exclusiones de ruta de acceso y proceso. 

Tenga en cuenta los siguientes puntos:

- *Las exclusiones de ruta de* acceso excluyen archivos específicos y cualquier acceso a esos archivos.
- *Las exclusiones de procesos* excluyen lo que toca un proceso, pero no excluyen el proceso en sí.
- Enumera las exclusiones de proceso con su ruta de acceso completa y no solo por su nombre. (El método de solo nombre es menos seguro).
- Si enumera cada archivo ejecutable (.exe) como una exclusión de ruta de acceso y una exclusión de proceso, se excluirá el proceso y lo que toque.


## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Configurar grupos de dispositivos, colecciones de dispositivos y unidades organizativas

Los grupos de dispositivos, las colecciones de dispositivos y las unidades organizativas permiten al equipo de seguridad administrar y asignar directivas de seguridad de forma eficaz y eficaz. En la tabla siguiente se describe cada uno de estos grupos y cómo configurarlos. Es posible que la organización no use los tres tipos de colección.

| Tipo de colección | Qué hacer |
|--|--|
|[Los grupos de dispositivos](/microsoft-365/security/defender-endpoint/machine-groups) (anteriormente denominados *grupos* de máquinas) permiten al equipo de operaciones de seguridad configurar funciones de seguridad, como la investigación automatizada y la corrección.<br/><br/>Los grupos de dispositivos también son útiles para asignar acceso a esos dispositivos para que el equipo de operaciones de seguridad pueda realizar acciones de corrección si es necesario. <br/><br/>Los grupos de dispositivos se [crean en Microsoft 365 Defender portal](microsoft-defender-security-center.md). |1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ).<br/>2. En el panel de navegación de la izquierda, elija **Configuración** Grupos de  >    >  **dispositivos de permisos de**  >  **extremos**.  <br/>3. Elija **+ Agregar grupo de dispositivos**.<br/>4. Especifique un nombre y una descripción para el grupo de dispositivos.<br/>5. En la **lista Nivel de automatización,** seleccione una opción. (Se recomienda **Full: corregir las amenazas automáticamente).)** Para obtener más información sobre los distintos niveles de automatización, vea [How threats are remediated](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated).<br/>6. Especifique las condiciones de una regla de coincidencia para determinar qué dispositivos pertenecen al grupo de dispositivos. Por ejemplo, puedes elegir un dominio, versiones del sistema operativo o incluso usar etiquetas [de dispositivo.](/microsoft-365/security/defender-endpoint/machine-tags)<br/>7. En la **pestaña Acceso de** usuario, especifique los roles que deben tener acceso a los dispositivos que se incluyen en el grupo de dispositivos. <br/>8. Elija **Listo**. |
|[Las colecciones de dispositivos](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) permiten al equipo de operaciones de seguridad administrar aplicaciones, implementar la configuración de cumplimiento o instalar actualizaciones de software en los dispositivos de la organización.<br/><br/>Las colecciones de dispositivos se crean mediante [Configuration Manager](/mem/configmgr/). |Siga los pasos de [Crear una colección](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[Las unidades](/azure/active-directory-domain-services/create-ou) organizativas permiten agrupar lógicamente objetos como cuentas de usuario, cuentas de servicio o cuentas de equipo.<br/><br/> A continuación, puede asignar administradores a unidades organizativas específicas y aplicar una directiva de grupo para aplicar las opciones de configuración de destino.<br/><br/> Las unidades organizativas se definen [en Azure Active Directory Domain Services](/azure/active-directory-domain-services). | Siga los pasos descritos [en Crear una unidad organizativa en un Azure Active Directory dominio administrado de Servicios de dominio](/azure/active-directory-domain-services/create-ou). |


## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena!** Ha completado la fase de configuración de [cambiar a Defender para endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)!

- [Continúe con la fase 3: Incorporación a Defender para el extremo](switch-to-microsoft-defender-onboard.md)
