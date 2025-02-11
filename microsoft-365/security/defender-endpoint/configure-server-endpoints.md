---
title: Incorporación de servidores Windows al servicio Microsoft Defender para punto de conexión
description: Incorpore servidores Windows para que puedan enviar datos del sensor al sensor de Microsoft Defender para punto de conexión.
keywords: onboard server, server, 2012r2, 2016, 2019, server onboarding, device management, configure Microsoft Defender para punto de conexión servers, onboard Microsoft Defender para punto de conexión servers, onboard servidores de Microsoft Defender para punto de conexión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
ms.date: 09/22/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 5a29b372aaa2cddb4d1c7c541e0070e900188d90
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68362041"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>Incorporación de servidores Windows al servicio Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- Windows Server 2012 R2
- Windows Server 2016
- Canal de Windows Server Semi-Annual Enterprise
- Windows Server 2019 y versiones posteriores
- Edición principal de Windows Server 2019
- Windows Server 2022
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configserver-abovefoldlink)

Defender para punto de conexión amplía la compatibilidad para incluir también el sistema operativo Windows Server. Esta compatibilidad proporciona funcionalidades avanzadas de detección e investigación de ataques sin problemas a través de la consola de Microsoft 365 Defender. La compatibilidad con Windows Server proporciona información más detallada sobre las actividades del servidor, la cobertura para la detección de ataques de kernel y memoria, y habilita las acciones de respuesta.

En este artículo se describe cómo incorporar servidores Windows específicos para Microsoft Defender para punto de conexión.

Para obtener instrucciones sobre cómo descargar y usar líneas base de Seguridad de Windows para servidores Windows, consulte [Seguridad de Windows líneas base](/windows/device-security/windows-security-baselines).

## <a name="windows-server-onboarding-overview"></a>Introducción a la incorporación de Windows Server

Tendrá que completar los pasos generales siguientes para incorporar correctamente los servidores.

:::image type="content" source="images/server-onboarding-tools-methods.png" alt-text="Ilustración del flujo de incorporación para servidores Windows y dispositivos Windows 10" lightbox="images/server-onboarding-tools-methods.png":::

>[!NOTE]
> No se admiten las ediciones de Windows Hyper-V Server.

**Integración con Microsoft Defender para servidores**:

Microsoft Defender para punto de conexión se integra perfectamente con Microsoft Defender para servidores. Puede incorporar servidores automáticamente, hacer que los servidores supervisados por Microsoft Defender for Cloud aparezcan en Defender para punto de conexión y realizar investigaciones detalladas como Microsoft Defender para el cliente en la nube. Para obtener más información, vaya a [Protección de los puntos de conexión con la solución EDR integrada de Defender for Cloud: Microsoft Defender para punto de conexión](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows)

> [!NOTE]
> Para Windows Server 2012 R2 y 2016, puede instalar o actualizar manualmente la solución moderna y unificada en estas máquinas, o bien usar la integración para implementar o actualizar automáticamente los servidores cubiertos por sus respectivos Microsoft Defender para el plan de servidor. Más información sobre cómo realizar el cambio en [Proteger los puntos de conexión con la solución EDR integrada de Defender for Cloud: Microsoft Defender para punto de conexión](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows#enable-the-integration).
> - Cuando se usa Microsoft Defender for Cloud para supervisar servidores, se crea automáticamente un inquilino de Defender para punto de conexión (en EE. UU. para usuarios de EE. UU., en la UE para usuarios europeos y en el Reino Unido para usuarios del Reino Unido).
Los datos recopilados por Defender para punto de conexión se almacenan en la ubicación geográfica del inquilino tal como se identifica durante el aprovisionamiento.
> - Si usa Defender para punto de conexión antes de usar Microsoft Defender for Cloud, los datos se almacenarán en la ubicación que especificó al crear el inquilino, incluso si se integra con Microsoft Defender for Cloud más adelante.
> - Una vez configurado, no se puede cambiar la ubicación donde se almacenan los datos. Si necesita mover los datos a otra ubicación, debe ponerse en contacto con Soporte técnico de Microsoft para restablecer el inquilino.
> - La supervisión de puntos de conexión de servidor que usan esta integración se ha deshabilitado para Office 365 clientes de GCC.
> - Los servidores Linux incorporados a través de Microsoft Defender for Cloud tendrán su configuración inicial establecida para ejecutar Antivirus de Defender en [modo pasivo](/defender-endpoint/microsoft-defender-antivirus-compatibility#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions).

**Windows Server 2012 R2 y Windows Server 2016**:

- Descarga de paquetes de instalación e incorporación
- Aplicar el paquete de instalación
- Siga los pasos de incorporación de la herramienta correspondiente.

**Windows Server Semi-Annual Enterprise Channel y Windows Server 2019**:

- Descarga del paquete de incorporación
- Siga los pasos de incorporación de la herramienta correspondiente.

>[!IMPORTANT]
>Para poder comprar Microsoft Defender para punto de conexión SKU de servidor, debe haber adquirido ya un mínimo combinado de cualquiera de las siguientes licencias de suscripción, Windows E5/A5, Microsoft 365 E5/A5 o Seguridad de Microsoft 365 E5.  Para obtener más información sobre las licencias, consulte los [Términos del producto](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/all).

## <a name="windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2012 R2 y Windows Server 2016

### <a name="new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution"></a>Nuevas funciones de Windows Server 2012 R2 y 2016 en la solución unificada moderna

La implementación anterior (antes de abril de 2022) de la incorporación de Windows Server 2012 R2 y Windows Server 2016 requería el uso de Microsoft Monitoring Agent (MMA).

El nuevo paquete de solución unificada facilita la incorporación de servidores mediante la eliminación de dependencias y los pasos de instalación. También proporciona un conjunto de características mucho más expandido. Para obtener más información, consulte [Defender Windows Server 2012 R2 y 2016](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292).

En función del servidor que esté incorporando, la solución unificada instala Microsoft Defender Antivirus o el sensor EDR. En la tabla siguiente se indica qué componente está instalado y qué está integrado de forma predeterminada.

|Versión del servidor|Av|Edr|
|----|----|----|
|Windows Server 2012 R2 SP1|![Sí.](images/svg/check-yes.svg)|![Sí.](images/svg/check-yes.svg)|
|Windows Server 2016|Integrado|![Sí.](images/svg/check-yes.svg)|
|Windows Server 2019 o posterior|Integrado|Integrado|

Si previamente ha incorporado los servidores mediante MMA, siga las instrucciones que se proporcionan en [Migración del servidor](server-migration.md) para migrar a la nueva solución.

> [!IMPORTANT]
> Antes de continuar con la incorporación, consulte la sección [Problemas conocidos y limitaciones del nuevo paquete de soluciones unificado para Windows Server 2012 R2 y 2016](#known-issues-and-limitations-in-the-new-unified-solution-package-for-windows-server-2012-r2-and-2016).

### <a name="prerequisites"></a>Requisitos previos

#### <a name="prerequisites-for-windows-server-2012-r2"></a>Requisitos previos para Windows Server 2012 R2

Si ha actualizado completamente las máquinas con el paquete [acumulativo mensual](https://support.microsoft.com/topic/windows-8-1-and-windows-server-2012-r2-update-history-47d81dd2-6804-b6ae-4112-20089467c7a6) más reciente, **no** hay otros requisitos previos y los requisitos siguientes ya se rellenarán.

El paquete del instalador comprobará si los siguientes componentes ya se han instalado mediante una actualización para evaluar si se han cumplido los requisitos mínimos para una instalación correcta:

- [Actualización de la experiencia del cliente y telemetría de diagnóstico](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)
- [Actualización de Universal C Runtime en Windows](https://support.microsoft.com/topic/update-for-universal-c-runtime-in-windows-c0514201-7fe6-95a3-b0a5-287930f3560c)
- [Actualización de seguridad para Windows Server 2012 R2 (KB3045999)](https://support.microsoft.com/en-us/topic/ms15-038-description-of-the-security-update-for-windows-april-14-2015-99265f07-6926-d6d2-5203-3b32b214a9c3)

#### <a name="prerequisites-for-windows-server-2016"></a>Requisitos previos para Windows Server 2016

- Se debe instalar la actualización de pila de mantenimiento (SSU) del 14 de septiembre de 2021 o posterior.
- Se debe instalar la última actualización acumulativa (LCU) del 20 de septiembre de 2018 o posterior.  Se recomienda instalar los SSU y LCU disponibles más recientes en el servidor.
- Habilite la característica Microsoft Defender Antivirus y asegúrese de que está actualizada. Para obtener más información sobre cómo habilitar antivirus de Defender en Windows Server, consulta [Volver a habilitar el Antivirus de Defender en Windows Server si se ha deshabilitado](enable-update-mdav-to-latest-ws.md#re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-disabled) y [Volver a habilitar el Antivirus de Defender en Windows Server si se ha desinstalado](enable-update-mdav-to-latest-ws.md#re-enable-microsoft-defender-antivirus-on-windows-server-if-it-was-uninstalled).
- Descargue e instale la versión más reciente de la plataforma mediante Windows Update. Como alternativa, descargue el paquete de actualización manualmente desde el [catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) o desde [MMPC](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64).

#### <a name="prerequisites-for-running-with-third-party-security-solutions"></a>Requisitos previos para la ejecución con soluciones de seguridad de terceros

Si tiene previsto usar una solución antimalware de terceros, deberá ejecutar Microsoft Defender Antivirus en modo pasivo. Debe recordar establecer en modo pasivo durante el proceso de instalación e incorporación. 

> [!NOTE]
> Si va a instalar Microsoft Defender para punto de conexión en servidores con McAfee Endpoint Security (ENS) o VirusScan Enterprise (VSE), es posible que sea necesario actualizar la versión de la plataforma de McAfee para asegurarse de que Microsoft Defender Antivirus no se quite ni deshabilite. Para obtener más información, incluidos los números de versión específicos necesarios, consulte el [artículo de McAfee Knowledge Center](https://kcm.trellix.com/corporate/index?page=content&id=KB88214).

#### <a name="update-packages-for-microsoft-defender-for-endpoint-on-windows-server-2012-r2-and-2016"></a>Actualizar paquetes para Microsoft Defender para punto de conexión en Windows Server 2012 R2 y 2016

Para recibir mejoras y correcciones periódicas del producto para el componente sensor EDR, asegúrese de que se aplique o apruebe Windows Update [KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277). Además, para mantener actualizados los componentes de protección, consulte [Administración de actualizaciones Microsoft Defender Antivirus y aplicación de líneas base](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions).

Si usa Windows Server Update Services (WSUS) o Configuration Manager de punto de conexión de Microsoft, esta nueva "actualización de Microsoft Defender para punto de conexión para el sensor EDR" está disponible en la categoría " Microsoft Defender para punto de conexión".

### <a name="onboarding-steps-summary"></a>Resumen de los pasos de incorporación

- PASO 1: [Descargar los paquetes de instalación e incorporación](#step-1-download-installation-and-onboarding-packages)
- PASO 2: [Aplicar el paquete de instalación e incorporación](#step-2-apply-the-installation-and-onboarding-package)
- PASO 3: [Completar los pasos de incorporación](#step-3-complete-the-onboarding-steps)

### <a name="step-1-download-installation-and-onboarding-packages"></a>PASO 1: Descarga de paquetes de instalación e incorporación

Tendrá que descargar los paquetes de **instalación** e **incorporación** desde el portal.

> [!NOTE]
> El paquete de instalación se actualiza mensualmente. Asegúrese de descargar el paquete más reciente antes del uso.
> Para actualizar después de la instalación, no es necesario volver a ejecutar el paquete del instalador. Si lo hace, el instalador le pedirá que se desconecte primero, ya que es un requisito para la desinstalación. Consulte [Actualización de paquetes para Microsoft Defender para punto de conexión en Windows Server 2012 R2 y 2016](#update-packages-for-microsoft-defender-for-endpoint-on-windows-server-2012-r2-and-2016).

> [!div class="mx-imgBorder"]
> ![Imagen del panel de incorporación](images/install-agent-onboard.png)

   > [!NOTE]
   > En Windows Server 2012R2, el paquete de instalación instalará Microsoft Defender Antivirus y estará activo a menos que lo establezcas en modo pasivo. En Windows Server 2016, Microsoft Defender Antivirus debe instalarse como una característica (consulte [Cambiar a MDE](/microsoft-365/security/defender-endpoint/switch-to-mde-phase-2#re-enable-microsoft-defender-antivirus-on-windows-server-2016)) primero y totalmente actualizado antes de continuar con la instalación.
   >
   > Si ejecuta una solución antimalware que no es de Microsoft, asegúrese de agregar exclusiones para Microsoft Defender Antivirus ([de esta lista de procesos de Microsoft Defender en la pestaña Procesos de Defender](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)) a la solución que no es de Microsoft antes de la instalación.  También se recomienda agregar soluciones de seguridad que no sean de Microsoft a la lista de exclusión del Antivirus de Defender.

El **paquete de instalación** contiene un archivo MSI que instala el agente de Microsoft Defender para punto de conexión.

El **paquete de incorporación** contiene los siguientes archivos:

- `OptionalParamsPolicy` : contiene la configuración que habilita la recopilación de ejemplos.
- `WindowsDefenderATPOnboardingScript.cmd` : contiene el script de incorporación.

Siga estos pasos para descargar los paquetes:

1. En Microsoft 365 Defender, vaya a **Configuración > Administración de dispositivos > Incorporación**.

2. Seleccione **Windows Server 2012 R2 y 2016**.

3. Seleccione **Descargar paquete de instalación** y guarde el archivo .msi.

4. Seleccione **Descargar paquete de incorporación** y guarde el archivo .zip.

5. Instale el paquete de instalación mediante cualquiera de las opciones para instalar Microsoft Defender Antivirus. La instalación requiere permisos administrativos.

### <a name="step-2-apply-the-installation-and-onboarding-package"></a>PASO 2: Aplicar el paquete de instalación e incorporación

En este paso, instalará los componentes de prevención y detección necesarios antes de incorporar el dispositivo al entorno de Microsoft Defender para punto de conexión nube, para preparar la máquina para la incorporación. Asegúrese de que se cumplen todos los [requisitos previos](#prerequisites) .

   > [!NOTE]
   > Microsoft Defender Antivirus se instalará y estará activo a menos que lo establezca en modo pasivo.

#### <a name="options-to-install-the-microsoft-defender-for-endpoint-packages"></a>Opciones para instalar los paquetes de Microsoft Defender para punto de conexión

En la sección anterior, descargó un paquete de instalación. El paquete de instalación contiene el instalador para todos los componentes de Microsoft Defender para punto de conexión.

Puede usar cualquiera de las siguientes opciones para instalar el agente:

- [Instalación mediante la línea de comandos](#install-microsoft-defender-for-endpoint-using-the-command-line)
- [Instalación mediante un script](#install-microsoft-defender-for-endpoint-using-a-script)
- [Aplicar los paquetes de instalación e incorporación mediante directiva de grupo](#apply-the-microsoft-defender-for-endpoint-installation-and-onboarding-packages-using-group-policy)

##### <a name="install-microsoft-defender-for-endpoint-using-the-command-line"></a>Instalación de Microsoft Defender Para punto de conexión mediante la línea de comandos

Use el paquete de instalación del paso anterior para instalar Microsoft Defender para punto de conexión.

Ejecute el siguiente comando para instalar Microsoft Defender para punto de conexión:

```console
Msiexec /i md4ws.msi /quiet
```

Para desinstalarlo, asegúrese de que la máquina se apaga primero mediante el script de offboarding adecuado. A continuación, use Panel de control \> Programas \> y características para realizar la desinstalación.

Como alternativa, ejecute el siguiente comando de desinstalación para desinstalar Microsoft Defender para punto de conexión:

```console
Msiexec /x md4ws.msi /quiet
```

Debe usar el mismo paquete que usó para la instalación para que el comando anterior se realice correctamente.

El `/quiet` modificador suprime todas las notificaciones.

> [!NOTE]
> Microsoft Defender Antivirus no entra automáticamente en modo pasivo. Puede optar por establecer Microsoft Defender Antivirus para que se ejecute en modo pasivo si ejecuta una solución antivirus o antimalware que no es de Microsoft. En el caso de las instalaciones de línea de comandos, la opción `FORCEPASSIVEMODE=1` establece inmediatamente el componente Microsoft Defender Antivirus en modo pasivo para evitar interferencias. A continuación, para asegurarse de que Antivirus de Defender permanece en modo pasivo después de incorporarse para admitir funcionalidades como EDR Block, establezca la clave del Registro "ForceDefenderPassiveMode".

La compatibilidad con Windows Server proporciona información más detallada sobre las actividades del servidor, la cobertura para la detección de ataques de kernel y memoria, y habilita las acciones de respuesta.

##### <a name="install-microsoft-defender-for-endpoint-using-a-script"></a>Instalación de Microsoft Defender para punto de conexión mediante un script

Puede usar el [script del asistente del instalador](server-migration.md#installer-script) para ayudar a automatizar la instalación, desinstalación e incorporación. 
> [!NOTE]
> El script de instalación está firmado. Cualquier modificación en el script invalidará la firma. Al descargar el script desde GitHub, el enfoque recomendado para evitar modificaciones accidentales consiste en descargar los archivos de origen como un archivo zip y, a continuación, extraerlo para obtener el archivo install.ps1 (en la página principal código, haga clic en el menú desplegable Código y seleccione "Descargar ZIP").

Este script se puede usar en varios escenarios, incluidos los que se describen en [Escenarios de migración del servidor de la solución de Microsoft Defender para punto de conexión anterior basada en MMA](/microsoft-365/security/defender-endpoint/server-migration) y para la implementación mediante directiva de grupo como se describe a continuación.

##### <a name="apply-the-microsoft-defender-for-endpoint-installation-and-onboarding-packages-using-group-policy"></a>Aplicar los paquetes de instalación e incorporación de Microsoft Defender para punto de conexión mediante la directiva de grupo

1. Cree una directiva de grupo: <br> Abra la [consola de administración de directiva de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón derecho en **directiva de grupo Objetos** que desea configurar y seleccione **Nuevo**. Escriba el nombre del nuevo GPO en el cuadro de diálogo que se muestra y seleccione **Aceptar**.

2. Abra la [consola de administración de directiva de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón derecho en el objeto de directiva de grupo (GPO) que desea configurar y seleccione **Editar**.

3. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo**, **Preferencias** y, a continuación, **Configuración del panel de control**.

4. Haga clic con el botón derecho en **Tareas programadas**, seleccione **Nuevo** y, a continuación, haga clic en **Tarea inmediata (al menos Windows 7).**

5. En la ventana **Tarea** que se abre, vaya a la pestaña **General** . En **Opciones de seguridad** , seleccione **Cambiar usuario o grupo** y escriba SYSTEM y, a continuación, seleccione **Comprobar nombres** y, a continuación, **Aceptar**. NT AUTHORITY\SYSTEM aparece como la cuenta de usuario como se ejecutará la tarea.

6. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla **Ejecutar con los privilegios más altos** .

7. En el campo Nombre, escriba un nombre adecuado para la tarea programada (por ejemplo, Implementación de Defender para punto de conexión).

8. Vaya a la pestaña **Acciones** y seleccione **Nuevo...** Asegúrese de que **Iniciar un programa** está seleccionado en el campo **Acción** . El [script del instalador](server-migration.md#installer-script) controla la instalación y realiza inmediatamente el paso de incorporación una vez completada la instalación. Seleccione *C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe* proporcione los argumentos:

    ```console
     -ExecutionPolicy RemoteSigned \\servername-or-dfs-space\share-name\install.ps1 -OnboardingScript \\servername-or-dfs-space\share-name\windowsdefenderatponboardingscript.cmd
    ```

    > [!NOTE]

    > La configuración de directiva de ejecución recomendada es `Allsigned`. Esto requiere la importación del certificado de firma del script en el almacén publicadores de confianza del equipo local si el script se ejecuta como SYSTEM en el punto de conexión.

    Reemplace \\servername-or-dfs-space\share-name por la ruta de acceso UNC mediante el nombre de dominio completo (FQDN) del servidor de archivos del archivo *install.ps1* compartido. El paquete del instalador md4ws.msi debe colocarse en el mismo directorio.  Asegúrese de que los permisos de la ruta de acceso UNC permiten el acceso de escritura a la cuenta de equipo que instala el paquete para admitir la creación de archivos de registro. Si desea deshabilitar la creación de archivos de registro (no recomendados), puede usar los parámetros -noETL -noMSILog.

    Para escenarios en los que quiera que Microsoft Defender Antivirus coexista con soluciones antimalware que no son de Microsoft, agregue el parámetro $Passive para establecer el modo pasivo durante la instalación.

9. Seleccione **Aceptar** y cierre las ventanas de GPMC abiertas.

10. Para vincular el GPO a una unidad organizativa (OU), haga clic con el botón derecho y seleccione **Vincular un GPO existente**. En el cuadro de diálogo que se muestra, seleccione el objeto directiva de grupo que desea vincular. Seleccione **Aceptar**.

Para obtener más opciones de configuración, vea [Configurar opciones de recopilación de ejemplo](configure-endpoints-gp.md#configure-sample-collection-settings) y [Otras opciones de configuración recomendadas](configure-endpoints-gp.md#other-recommended-configuration-settings).

### <a name="step-3-complete-the-onboarding-steps"></a>PASO 3: Completar los pasos de incorporación

Los pasos siguientes solo son aplicables si usa una solución antimalware de terceros. Tendrá que aplicar la siguiente configuración Microsoft Defender modo pasivo Antivirus. Compruebe que se ha configurado correctamente:

1. Establezca la siguiente entrada del Registro:
    - Camino: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
    - Nombre: `ForceDefenderPassiveMode`
    - Tipo: `REG_DWORD`
    - Valor: `1`

   :::image type="content" source="images/atp-verify-passive-mode.png" alt-text="Resultado de la comprobación del modo pasivo" lightbox="images/atp-verify-passive-mode.png":::

> [!IMPORTANT]
>
> - Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar directiva de grupo o Configuration Manager de punto de conexión de Microsoft.

#### <a name="known-issues-and-limitations-in-the-new-unified-solution-package-for-windows-server-2012-r2-and-2016"></a>Problemas conocidos y limitaciones en el nuevo paquete de soluciones unificado para Windows Server 2012 R2 y 2016

Descargue siempre el paquete del instalador más reciente antes de realizar una nueva instalación. Después de la instalación, asegúrese de actualizar periódicamente mediante las actualizaciones de componentes descritas en la sección [Actualizar paquetes para Microsoft Defender para punto de conexión en Windows Server 2012 R2 y 2016](#update-packages-for-microsoft-defender-for-endpoint-on-windows-server-2012-r2-and-2016). Los siguientes detalles se aplican al nuevo paquete de solución unificada para Windows Server 2012 R2 y 2016:

- Una actualización del sistema operativo puede presentar un problema de instalación en máquinas con discos más lentos debido a un tiempo de espera con la instalación del servicio. Se produce un error en la instalación con el mensaje "No se encontró c:\archivos de programa\windows defender\mpasdesc.dll, - 310 WinDefend". Use el paquete de instalación más reciente y el script [ deinstall.ps1](https://github.com/microsoft/mdefordownlevelserver) más reciente para ayudar a borrar la instalación con errores si es necesario.
- Asegúrese de que se cumplen los requisitos de conectividad especificados en [Habilitar el acceso a Microsoft Defender para punto de conexión direcciones URL del servicio en el servidor proxy](/microsoft-365/security/defender-endpoint/configure-proxy-internet?enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server). Son equivalentes a esos requisitos para Windows Server 2019.
- Hemos identificado un problema con la conectividad de Windows Server 2012 R2 a la nube cuando se usa TelemetryProxyServer estático **y** no se puede acceder a las direcciones URL de la lista de revocación de certificados (CRL) desde el contexto de la cuenta system. La mitigación inmediata consiste en usar una opción de proxy alternativa ("todo el sistema") que proporcione dicha conectividad o configurar el mismo proxy mediante la configuración de WinInet en el contexto de la cuenta SYSTEM.
Como alternativa, use las instrucciones proporcionadas en [Solución alternativa para un problema conocido con TelemetryProxyServer en máquinas desconectadas](#workaround-for-a-known-issue-with-telemetryproxyserver-on-disconnected-machines) para instalar un certificado como solución alternativa.
- Anteriormente, el uso de Microsoft Monitoring Agent (MMA) en Windows Server 2016 y versiones posteriores permitía que la puerta de enlace de OMS/Log Analytics proporcionara conectividad a los servicios en la nube de Defender. La nueva solución, como Microsoft Defender para punto de conexión en Windows Server 2019, Windows Server 2022 y Windows 10, no admite esta puerta de enlace.
- En Windows Server 2016, compruebe que Microsoft Defender Antivirus está instalado, está activo y actualizado. Puede descargar e instalar la versión más reciente de la plataforma mediante Windows Update. Como alternativa, descargue el paquete de actualización manualmente desde el [catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) o desde [MMPC](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64).
- En Windows Server 2012 R2, no hay ninguna interfaz de usuario para Microsoft Defender Antivirus. Además, la interfaz de usuario en Windows Server 2016 solo permite operaciones básicas. Para realizar operaciones en un dispositivo localmente, consulte [Administración de Microsoft Defender para punto de conexión con PowerShell, WMI y MPCmdRun.exe](/microsoft-365/security/defender-endpoint/manage-mde-post-migration-other-tools). Como resultado, es posible que las características que dependen específicamente de la interacción del usuario, como dónde se solicita al usuario que tome una decisión o realice una tarea específica, no funcionen según lo esperado. Se recomienda deshabilitar o no habilitar la interfaz de usuario ni requerir la interacción del usuario en cualquier servidor administrado, ya que puede afectar a la funcionalidad de protección.
- No todas las reglas de reducción de superficie expuesta a ataques están disponibles en todos los sistemas operativos. Consulta [Reglas de reducción de superficie expuesta a ataques (ASR).](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules)
- Para habilitar [La protección de red](/microsoft-365/security/defender-endpoint/network-protection), se requieren más configuraciones:
  - `Set-MpPreference -EnableNetworkProtection Enabled`
  - `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`
  - `Set-MpPreference -AllowNetworkProtectionDownLevel 1`
  - `Set-MpPreference -AllowDatagramProcessingOnWinServer 1`

  Además, en máquinas con un gran volumen de tráfico de red, se recomienda encarecidamente realizar pruebas de rendimiento en su entorno antes de habilitar esta funcionalidad de forma amplia. Es posible que tenga que tener en cuenta el consumo de recursos adicional.
- No se admiten las actualizaciones del sistema operativo. Después, desinstale antes de actualizar.
- Las exclusiones automáticas de **los roles de servidor** no se admiten en Windows Server 2012 R2; sin embargo, las exclusiones integradas para los archivos del sistema operativo son. Para obtener más información sobre cómo agregar exclusiones, consulte [Recomendaciones de análisis de virus para equipos enterprise que ejecutan versiones compatibles actualmente de Windows](https://support.microsoft.com/topic/virus-scanning-recommendations-for-enterprise-computers-that-are-running-currently-supported-versions-of-windows-kb822158-c067a732-f24a-9079-d240-3733e39b40bc).
- En las máquinas que se han actualizado desde la solución anterior basada en MMA y el sensor EDR es una versión (versión preliminar) anterior a 10.8047.22439.1056, la desinstalación y reversión a la solución basada en MMA puede provocar bloqueos. Si está en una versión preliminar de este tipo, actualice con KB5005292.
- Para implementar e incorporar la nueva solución mediante Microsoft Endpoint Configuration Manager (MECM) en las versiones 2107 y 2203, esto requiere la creación de un paquete. Para obtener más información sobre cómo implementar programas y scripts en Configuration Manager, consulte [Paquetes y programas en Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs). También puede usar MECM 2107, 2203 para migrar desde la versión basada en MMA. Para obtener más información, consulte [Migración de servidores de Microsoft Monitoring Agent a la solución unificada](application-deployment-via-mecm.md).
- MECM 2107 con el paquete acumulativo de revisiones o posterior es necesario para admitir la administración de configuración de directivas mediante el nodo Endpoint Protection. 
- Microsoft Endpoint Configuration Manager 2207 o posterior admite la [instalación e incorporación automatizadas](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#bkmk_2207)

#### <a name="workaround-for-a-known-issue-with-telemetryproxyserver-on-disconnected-machines"></a>Solución alternativa para un problema conocido con TelemetryProxyServer en máquinas desconectadas

Descripción del problema: al usar la configuración TelemetryProxyServer para especificar un proxy que usará el componente EDR de Microsoft Defender para punto de conexión, en equipos que no tienen otra manera de acceder a la dirección URL de la lista de revocación de certificados (CRL), si falta un certificado intermedio, el sensor EDR no se conectará correctamente al servicio en la nube.

Escenario afectado: -Microsoft Defender para punto de conexión con el número de versión de Sense 10.8048.22439.1065 o versiones preliminares anteriores que se ejecutan en Windows Server 2012 R2:Uso de la configuración del proxy TelemetryProxyServer; otros métodos no se ven afectados

Solución:
1. Asegúrese de que la máquina ejecuta sense versión 10.8048.22439.1065 o superior mediante la instalación con el paquete más reciente disponible en la página de incorporación o aplicando KB5005292.
2. Descargar y descomprimir el certificado desde https://github.com/microsoft/mdefordownlevelserver/blob/main/InterCA.zip
3. Importe el certificado al almacén "Entidades de certificación intermedias" de confianza del equipo local.
Puede usar el comando de PowerShell: Import-Certificate -FilePath .\InterCA.cer -CertStoreLocation Cert:\LocalMachine\Ca

## <a name="windows-server-semi-annual-enterprise-channel-sac-windows-server-2019-and-windows-server-2022"></a>Windows Server Semi-Annual Enterprise Channel (SAC), Windows Server 2019 y Windows Server 2022

### <a name="download-package"></a>Descargar paquete

1. En Microsoft 365 Defender, vaya a **Configuración > Administración de dispositivos > Incorporación**.

2. Seleccione **Windows Server 1803 y 2019**.

3. Seleccione **Descargar paquete**. Guárdelo como WindowsDefenderATPOnboardingPackage.zip.

4. Siga los pasos proporcionados en la sección [Completar los pasos de incorporación](#step-3-complete-the-onboarding-steps) .

## <a name="verify-the-onboarding-and-installation"></a>Comprobación de la incorporación y la instalación

Compruebe que Microsoft Defender Antivirus y Microsoft Defender para punto de conexión están en ejecución.

## <a name="run-a-detection-test-to-verify-onboarding"></a>Ejecución de una prueba de detección para comprobar la incorporación

Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que un dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md).

> [!NOTE]
> No es necesario ejecutar Microsoft Defender Antivirus, pero se recomienda. Si otro producto de proveedor de antivirus es la solución de endpoint protection principal, puede ejecutar Antivirus de Defender en modo pasivo. Solo puede confirmar que el modo pasivo está activado después de comprobar que se está ejecutando Microsoft Defender para punto de conexión sensor (SENSE).

1. Ejecute el siguiente comando para comprobar que Microsoft Defender Antivirus está instalado:

    > [!NOTE]
    > Este paso de comprobación solo es necesario si usa Microsoft Defender Antivirus como solución antimalware activa.

    ```DOS
    sc.exe query Windefend
    ```

    Si el resultado es "El servicio especificado no existe como un servicio instalado", deberá instalar Microsoft Defender Antivirus.

    Para obtener información sobre cómo usar directiva de grupo para configurar y administrar Microsoft Defender Antivirus en los servidores windows, consulte [Uso de directiva de grupo configuración para configurar y administrar Microsoft Defender Antivirus](use-group-policy-microsoft-defender-antivirus.md).

2. Ejecute el siguiente comando para comprobar que Microsoft Defender para punto de conexión se está ejecutando:

    ```DOS
    sc.exe query sense
    ```

    El resultado debe mostrar que se está ejecutando. Si tiene problemas con la incorporación, consulte [Solución de problemas de incorporación](troubleshoot-onboarding.md).

## <a name="run-a-detection-test"></a>Ejecución de una prueba de detección

Siga los pasos descritos en [Ejecutar una prueba de detección en un dispositivo recién incorporado](run-detection-test.md) para comprobar que el servidor informa a Defender para el servicio de punto de conexión.

## <a name="next-steps"></a>Pasos siguientes

Después de incorporar correctamente los dispositivos al servicio, deberá configurar los componentes individuales de Microsoft Defender para punto de conexión. Siga el [orden de adopción](prepare-deployment.md#adoption-order) que se va a guiar para habilitar los distintos componentes.

## <a name="offboard-windows-servers"></a>Servidores Windows fuera del panel

Puede desconectar Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC), Windows Server 2019 y la edición Windows Server 2019 Core en el mismo método disponible para Windows 10 dispositivos cliente.

- [Dispositivos fuera del panel que usan directiva de grupo](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Dispositivos fuera de la placa con Configuration Manager](configure-endpoints-sccm.md#offboard-devices-using-configuration-manager)
- [Dispositivos fuera del panel con herramientas de mobile Administración de dispositivos](configure-endpoints-mdm.md#offboard-devices-using-mobile-device-management-tools)
- [Dispositivos fuera del panel con un script local](configure-endpoints-script.md#offboard-devices-using-a-local-script)

Después del offboarding, puede continuar con la desinstalación del paquete de solución unificado en Windows Server 2012 R2 y Windows Server 2016.

Para otras versiones de Windows Server, tiene dos opciones para desconectar servidores Windows del servicio:

- Desinstalación del agente mma
- Quitar la configuración del área de trabajo de Defender para punto de conexión

> [!NOTE]
> Estas instrucciones de eliminación para otras versiones de Windows Server también se aplican si ejecuta la Microsoft Defender para punto de conexión anterior para Windows Server 2016 y Windows Server 2012 R2 que requiere el MMA. Las instrucciones para migrar a la nueva solución unificada se encuentran [en escenarios de migración del servidor en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/server-migration).

## <a name="related-articles"></a>Artículos relacionados

- [Incorporar versiones anteriores de Windows](onboard-downlevel.md)
- [Incorporar dispositivos Windows 10 mediante la directiva de grupo](configure-endpoints.md)
- [Incorporar dispositivos que no tienen Windows](configure-endpoints-non-windows.md)
- [Configurar las opciones del proxy y de conectividad a Internet](configure-proxy-internet.md)
- [Ejecución de una prueba de detección en un dispositivo Defender para punto de conexión recién incorporado](run-detection-test.md)
- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
