---
title: McAfee to Microsoft Defender for Endpoint - Setup
description: Esta es la fase 2, Configuración, para migrar de McAfee a Microsoft Defender para endpoint.
keywords: migración, Microsoft Defender para Endpoint, edr
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 6fb6f6ccb6b30804788a147ab2db425a88998131
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538020"
---
# <a name="migrate-from-mcafee---phase-2-set-up-microsoft-defender-for-endpoint"></a>Migrar desde McAfee- Fase 2: Configurar Microsoft Defender para endpoint

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Preparación](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Fase 1: Preparación](mcafee-to-microsoft-defender-prepare.md) |![Fase 2: Configuración](images/phase-diagrams/setup.png)<br/>Fase 2: Configuración |[![Fase 3: Incorporación](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Fase 3: Incorporación](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
||*¡Estás aquí!* | |

**Bienvenido a la fase de instalación [de la migración de McAfee Endpoint Security (McAfee) a Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**. Esta fase incluye los siguientes pasos:

1. [Reinstale o habilite Antivirus de Microsoft Defender en los puntos de conexión](#reinstall-or-enable-microsoft-defender-antivirus-on-your-endpoints).

2. [Configurar Defender para endpoint](#configure-defender-for-endpoint).

3. [Agregue Microsoft Defender para endpoint a la lista de exclusión de McAfee](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee).

4. [Agregue McAfee a la lista de exclusión de Antivirus de Microsoft Defender](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus).

5. [Configure los grupos de dispositivos, las colecciones de dispositivos y las unidades organizativas.](#set-up-your-device-groups-device-collections-and-organizational-units)

6. [Configurar directivas antimalware y protección en tiempo real](#configure-antimalware-policies-and-real-time-protection).

## <a name="reinstall-or-enable-microsoft-defender-antivirus-on-your-endpoints"></a>Reinstalar o habilitar Antivirus de Microsoft Defender en los puntos de conexión

En ciertas versiones de Windows, Antivirus de Microsoft Defender probablemente se desinstala o deshabilita cuando se instaló la solución antivirus o antimalware que no es de Microsoft. Para obtener más información, [vea Antivirus de Microsoft Defender compatibilidad](microsoft-defender-antivirus-compatibility.md).

En Windows cliente, cuando se instala una solución antivirus o antimalware que no sea de Microsoft, Antivirus de Microsoft Defender se deshabilita automáticamente hasta que esos dispositivos se incorpore a Defender para endpoint. Cuando los extremos de cliente se incorporen a Defender for Endpoint, Antivirus de Microsoft Defender pasa al modo pasivo hasta que se desinstala la solución antivirus que no es de Microsoft. Antivirus de Microsoft Defender debe instalarse, pero es probable que esté deshabilitada en este punto del proceso de migración. A menos Antivirus de Microsoft Defender se haya desinstalado, no es necesario realizar ninguna acción para los Windows cliente.

En Windows, cuando se instala un antivirus o antimalware que no es de Microsoft, Antivirus de Microsoft Defender se deshabilita manualmente (si no se desinstala). Las siguientes tareas ayudan a garantizar que Antivirus de Microsoft Defender está instalado y establecido en modo pasivo en Windows Server.

Este paso del proceso de migración incluye las siguientes tareas:
- [Establecer DisableAntiSpyware en false en Windows Server](#set-disableantispyware-to-false-on-windows-server) (solo si es necesario)
- [Reinstalar Antivirus de Microsoft Defender en Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server);
- [Establecer Antivirus de Microsoft Defender modo pasivo en Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Establecer DisableAntiSpyware en false en Windows Server

La clave del Registro [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) se usó en el pasado para deshabilitar Antivirus de Microsoft Defender y para implementar otro producto antivirus, como McAfee. En general, no debe tener esta clave del Registro en los Windows dispositivos y puntos de conexión; sin embargo, si ha configurado, aquí le indicamos cómo establecer `DisableAntiSpyware` su valor en false:

1. En el dispositivo Windows server, abra el Editor del Registro.

2. Vaya a `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. En esa carpeta, busque una entrada DWORD denominada **DisableAntiSpyware**.

   - Si no ve esa entrada, está todo establecido.

   - Si ves **DisableAntiSpyware,** continúa con el paso 4.

4. Haga clic con el botón secundario en el DWORD DisableAntiSpyware y, a continuación, elija **Modificar**.

5. Establezca el valor en `0` . (Esto establece el valor de la clave del Registro en *false*.)

> [!TIP]
> Para obtener más información acerca de esta clave del Registro, [vea DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware).

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Reinstalar Antivirus de Microsoft Defender en Windows Server

> [!NOTE]
> El siguiente procedimiento solo se aplica a los puntos de conexión o dispositivos que ejecutan las siguientes versiones de Windows:
> - Windows Server 2019
> - Windows Servidor, versión 1803 (modo de solo núcleo)
> - Windows Server 2016

1. Como administrador local en el punto de conexión o dispositivo, abra Windows PowerShell.

2. Ejecute los siguientes cmdlets de PowerShell: <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>

   > [!NOTE]
   > Cuando se usa el comando DISM en una secuencia de tareas que ejecuta PS, se requiere la siguiente ruta de cmd.exe.
   > Ejemplos:
   >
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
   >
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Para comprobar Antivirus de Microsoft Defender se está ejecutando, use el siguiente cmdlet de PowerShell: <br/>
   
   `Get-Service -Name windefend`

   Busque un estado de *Ejecución*.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server

1. Abra el Editor del Registro y, a continuación, vaya a `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` .

2. Edite (o cree) una entrada DWORD denominada **ForcePassiveMode** y especifique la siguiente configuración:

   - Establezca el valor de DWORD en `1` .

   - En Base, seleccione **Hexadecimal**.

> [!NOTE]
> Después de incorporarse a Defender for Endpoint, es posible que deba establecer Antivirus de Microsoft Defender modo pasivo en Windows Server.

### <a name="are-you-using-windows-server-2016"></a>¿Estás usando Windows Server 2016?

Si tiene puntos de conexión que Windows Server 2016, no puede ejecutar Antivirus de Microsoft Defender junto con una solución antivirus o antimalware que no sea de Microsoft. Antivirus de Microsoft Defender se puede ejecutar en modo pasivo en Windows Server 2016. En este caso, deberá desinstalar la solución antivirus o antimalware que no sea de Microsoft e instalar o habilitar Antivirus de Microsoft Defender en su lugar. Para obtener más información, vea [Compatibilidad de soluciones antivirus con Defender para endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-compatibility).

Si está usando Windows Server 2016 y tiene problemas para habilitar Antivirus de Microsoft Defender, use el siguiente cmdlet de PowerShell:

`mpcmdrun -wdenable`

Para obtener más información, [vea Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server

Dado que su organización sigue usando McAfee, debe establecer Antivirus de Microsoft Defender en modo pasivo. De este modo, McAfee y Antivirus de Microsoft Defender pueden ejecutarse en paralelo hasta que haya terminado de incorporarse a Defender for Endpoint.

1. Abra el Editor del Registro y, a continuación, vaya a <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Edite (o cree) una entrada DWORD denominada **ForcePassiveMode** y especifique la siguiente configuración:
   
   - Establezca el valor de DWORD en **1**.
   
   - En **Base**, seleccione **Hexadecimal**.

> [!NOTE]
> Puede usar otros métodos para establecer la clave del Registro, como los siguientes:
>- [Preferencia de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Un paquete en Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="configure-defender-for-endpoint"></a>Configurar Defender para el extremo

Este paso del proceso de migración implica la configuración de Defender para Endpoint. Se recomienda usar Intune; sin embargo, puede cualquiera de los métodos que se enumeran en la tabla siguiente:

|Método  |Qué hacer  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <p>**NOTA:** Intune ahora forma parte de Microsoft Endpoint Manager. |1. Vaya al Centro [Microsoft Endpoint Manager administración e](https://go.microsoft.com/fwlink/?linkid=2109431) inicie sesión.<p>2. Seleccione **Perfiles**  >  **de configuración de dispositivos** y, a continuación, seleccione el tipo de perfil que desea configurar. <br/>Si aún no has creado un tipo de perfil de **restricciones** de dispositivo o quieres crear uno nuevo, consulta Configurar la configuración de restricción de dispositivo en [Microsoft Intune](/intune/device-restrictions-configure).<p>3. Seleccione **Propiedades** y, a continuación, **seleccione Configuración: Editar**.<p>4. Expanda **Antivirus de Microsoft Defender**. <p>5. Habilitar la **protección entregada en la nube.**<p>6. En la lista desplegable Preguntar a **los usuarios antes del** envío de ejemplo, seleccione Enviar todos los ejemplos **automáticamente.**<p>7. En el desplegable **Detectar aplicaciones potencialmente no deseadas,** seleccione **Habilitar** o **Auditar**.<p>8. Seleccione **Revisar + guardar** y, a continuación, elija **Guardar**.<p>Para obtener más información acerca de los perfiles de dispositivo de Intune, incluido cómo crear y configurar sus opciones, consulte ¿Qué Microsoft Intune [perfiles de dispositivo?](/intune/device-profiles).|
|Panel de control en Windows     |Siga las instrucciones aquí: [Activar Antivirus de Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows). <p>**NOTA**: Es posible que vea *Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows.        |
|[Administración de directivas de grupo avanzadas](/microsoft-desktop-optimization-pack/agpm/) <br/>o<br/>[Consola de administración de directivas de grupo](use-group-policy-microsoft-defender-antivirus.md)  |1. Vaya a `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <p>2. Busque una directiva denominada **Desactivar Antivirus de Microsoft Defender**.<p>3. Elija **Editar configuración de directiva** y asegúrese de que la directiva está deshabilitada. Esto permite Antivirus de Microsoft Defender. <p>**NOTA**: Es posible que vea *Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows. |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee"></a>Agregar Microsoft Defender para endpoint a la lista de exclusión de McAfee

Este paso del proceso de configuración implica agregar Defender for Endpoint a la lista de exclusión de McAfee y cualquier otro producto de seguridad que su organización esté usando. 

> [!TIP]
> Para obtener ayuda para configurar exclusiones, consulte la documentación de McAfee, como el siguiente [artículo: McAfee Endpoint Security 10.5.0 - Guía](https://docs.mcafee.com/bundle/endpoint-security-10.5.0-threat-prevention-product-guide-epolicy-orchestrator-windows/page/GUID-71C5FB4B-A143-43E6-8BF0-8B2C16ABE6DA.html)del producto del módulo de prevención de amenazas (McAfee ePolicy Orchestrator) - Windows: Configuración de exclusiones .

Las exclusiones específicas que se van a configurar dependen de la versión de Windows que se estén ejecutando los puntos de conexión o dispositivos y se enumeran en la tabla siguiente:

|Sistema operativo |Exclusiones |
|--|--|
| Windows 10, [versión 1803](/windows/release-health/status-windows-10-1803) o posterior (vea [Windows 10 de la versión )](/windows/release-health/release-information)<p>Windows 10, versión 1703 [o 1709](/windows/release-health/status-windows-10-1709) con [KB4493441](https://support.microsoft.com/help/4493441) instalado <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Servidor, versión 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
| [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**NOTA:** Donde los archivos temporales de host de supervisión 6\45 pueden ser subcarpetas numeradas diferentes.<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Agregar McAfee a la lista de exclusión para Antivirus de Microsoft Defender

Durante este paso del proceso de configuración, debe agregar McAfee y sus otras soluciones de seguridad a la Antivirus de Microsoft Defender de exclusión. 

Al agregar [exclusiones a los Antivirus de Microsoft Defender,](configure-exclusions-microsoft-defender-antivirus.md)debe agregar exclusiones de ruta de acceso y proceso. 

Puede elegir entre varios métodos para agregar las exclusiones a Antivirus de Microsoft Defender, como se muestra en la tabla siguiente:

|Método | Qué hacer|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <p>**NOTA:** Intune ahora forma parte de Microsoft Endpoint Manager. |1. Vaya al Centro [Microsoft Endpoint Manager administración e](https://go.microsoft.com/fwlink/?linkid=2109431) inicie sesión.<p>2. Seleccione **Perfiles**  >  **de configuración de dispositivos** y, a continuación, seleccione el perfil que desea configurar.<p>3. En **Administrar**, seleccione **Propiedades**. <p>4. Seleccione **Configuración: Editar**.<p>5. Expanda **Antivirus de Microsoft Defender** y, a continuación, expanda **Antivirus de Microsoft Defender exclusiones**.<p>6. Especifique los archivos y carpetas, las extensiones y los procesos que se excluirán de Antivirus de Microsoft Defender análisis. Para obtener referencia, [vea Antivirus de Microsoft Defender exclusiones](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions).<p>7. Elija **Revisar + guardar** y, a continuación, elija **Guardar**.  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. Con la consola [de Configuration Manager,](/mem/configmgr/core/servers/manage/admin-console)vaya a **Assets and Compliance** Endpoint Protection Antimalware Policies y, a continuación, seleccione la directiva  >    >  que desea modificar. <p>2. Especifique la configuración de exclusión de archivos y carpetas, extensiones y procesos que se excluirán de Antivirus de Microsoft Defender análisis. |
|[Objeto de directiva de grupo](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.<p>2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo** y haga clic en **Plantillas administrativas.**<p>3. Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > exclusiones**.<br/>**NOTA**: Es posible que vea *Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows.<p>4. Haga doble clic en la configuración **Exclusiones de ruta de** acceso y agregue las exclusiones.<br/>- Establezca la opción en **Habilitado**.<br/>- En la **sección Opciones,** haga clic **en Mostrar...**.<br/>- Especifique cada carpeta en su propia línea en la **columna Nombre de** valor.<br/>- Si especifica un archivo, asegúrese de escribir una ruta de acceso completa al archivo, incluida la letra de unidad, la ruta de acceso de carpeta, el nombre de archivo y la extensión. Escriba **0** en la **columna** Valor.<p>5. Haga clic en **Aceptar**.<p>6. Haga doble clic en la configuración **Exclusiones de extensión** y agregue las exclusiones.<br/>- Establezca la opción en **Habilitado**.<br/>- En la **sección Opciones,** haga clic **en Mostrar...**.<br/>- Escriba cada extensión de archivo en su propia línea en la **columna Nombre de** valor.  Escriba **0** en la **columna** Valor.<p>7. Haga clic en **Aceptar**. |
|Objeto de directiva de grupo local |1. En el punto de conexión o el dispositivo, abra el Editor de directivas de grupo local. <p>2. Vaya a **Configuración del** equipo Plantillas administrativas Windows  >    >  **componentes**  >  **Antivirus de Microsoft Defender**  >  **exclusiones**. <p>**NOTA**: Es posible que vea *Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows.<p>3. Especifique la ruta de acceso y las exclusiones de procesos. |
|Clave del Registro |1. Exporte la siguiente clave del Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Importe la clave del Registro. A continuación, se indican dos ejemplos:<br/>- Ruta de acceso local: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Recurso compartido de red: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

Tenga en cuenta los siguientes puntos:

- Las exclusiones de ruta de acceso excluyen archivos específicos y cualquier acceso a esos archivos.

- Las exclusiones de procesos excluyen lo que toca un proceso, pero no excluyen el proceso en sí.

- Si enumera cada archivo ejecutable (.exe) como una exclusión de ruta de acceso y una exclusión de proceso, se excluirá el proceso y lo que toque.

- Enumera las exclusiones de proceso con su ruta de acceso completa y no solo por su nombre. (El método de solo nombre es menos seguro).

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Configurar grupos de dispositivos, colecciones de dispositivos y unidades organizativas

| Tipo de colección | Qué hacer |
|--|--|
|[Los grupos de dispositivos](machine-groups.md) (anteriormente denominados grupos de máquinas) permiten al equipo de operaciones de seguridad configurar funciones de seguridad, como la investigación automatizada y la corrección.<p> Los grupos de dispositivos también son útiles para asignar acceso a esos dispositivos para que el equipo de operaciones de seguridad pueda realizar acciones de corrección si es necesario. <p>Los grupos de dispositivos se crean en el Centro de seguridad de Microsoft Defender. |1. Vaya al Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. En el panel de navegación de la izquierda, **elija Configuración** permisos Grupos de  >    >  **dispositivos**.  <p>3. Elija **+ Agregar grupo de dispositivos**.<p>4. Especifique un nombre y una descripción para el grupo de dispositivos.<p>5. En la **lista Nivel de automatización,** seleccione una opción. (Se recomienda **Full: corregir las amenazas automáticamente).)** Para obtener más información sobre los distintos niveles de automatización, vea [How threats are remediated](automated-investigations.md#how-threats-are-remediated).<p>6. Especifique las condiciones de una regla de coincidencia para determinar qué dispositivos pertenecen al grupo de dispositivos. Por ejemplo, puedes elegir un dominio, versiones del sistema operativo o incluso usar etiquetas [de dispositivo.](machine-tags.md) <p>7. En la **pestaña Acceso de** usuario, especifique los roles que deben tener acceso a los dispositivos que se incluyen en el grupo de dispositivos. <p>8. Elija **Listo**. |
|[Las colecciones de dispositivos](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) permiten al equipo de operaciones de seguridad administrar aplicaciones, implementar la configuración de cumplimiento o instalar actualizaciones de software en los dispositivos de la organización. <p>Las colecciones de dispositivos se crean mediante [Configuration Manager](/mem/configmgr/). |Siga los pasos de [Crear una colección](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[Las unidades](/azure/active-directory-domain-services/create-ou) organizativas permiten agrupar lógicamente objetos como cuentas de usuario, cuentas de servicio o cuentas de equipo. A continuación, puede asignar administradores a unidades organizativas específicas y aplicar una directiva de grupo para aplicar las opciones de configuración de destino.<p> Las unidades organizativas se definen [en Azure Active Directory Domain Services](/azure/active-directory-domain-services). | Siga los pasos descritos [en Crear una unidad organizativa en un Azure Active Directory dominio administrado de Servicios de dominio](/azure/active-directory-domain-services/create-ou). |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Configurar directivas antimalware y protección en tiempo real

Con Configuration Manager y las colecciones de dispositivos, configure las directivas de antimalware.

- Vea [Create and deploy antimalware policies for Endpoint Protection in Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies).

- Mientras crea y configura las directivas antimalware, asegúrese de revisar la configuración de protección en tiempo [real](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) y [habilitar el bloqueo a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md).

> [!TIP]
> Puedes implementar las directivas antes de que los dispositivos de la organización se incorpore.

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena!** Ha completado la fase de configuración de [la migración de McAfee a Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!

- [Continúe con la fase 3: Incorporación a Defender para el extremo](mcafee-to-microsoft-defender-onboard.md)
