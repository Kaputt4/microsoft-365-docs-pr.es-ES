---
title: Solución de problemas de incorporación de Microsoft Defender para punto de conexión
description: Solucione los problemas que puedan surgir durante la incorporación de dispositivos o al servicio Microsoft Defender para punto de conexión.
keywords: solución de problemas de incorporación, incorporación, visor de eventos, recopilación de datos y compilaciones de versión preliminar, datos y diagnósticos del sensor
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 7b2253e356b4ed4fb905ec4637d3f976e6e38d21
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67686975"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-onboarding-issues"></a>Solución de problemas de incorporación de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Es posible que tenga que solucionar el proceso de incorporación de Microsoft Defender para punto de conexión si encuentra problemas.
En esta página se proporcionan pasos detallados para solucionar problemas de incorporación que pueden producirse al implementar con una de las herramientas de implementación y errores comunes que pueden producirse en los dispositivos.

Antes de empezar a solucionar problemas con las herramientas de incorporación, es importante comprobar si se cumplen los requisitos mínimos para la incorporación de dispositivos a los servicios. [Obtenga información sobre los requisitos de licencias, hardware y software para incorporar dispositivos al servicio](minimum-requirements.md).

## <a name="troubleshoot-issues-with-onboarding-tools"></a>Solución de problemas con las herramientas de incorporación

Si ha completado el proceso de incorporación y no ve dispositivos en la [lista Dispositivos](investigate-machines.md) después de una hora, podría indicar un problema de incorporación o conectividad.

### <a name="troubleshoot-onboarding-when-deploying-with-group-policy"></a>Solución de problemas de incorporación al implementar con directiva de grupo

La implementación con directiva de grupo se realiza mediante la ejecución del script de incorporación en los dispositivos. La consola de directiva de grupo no indica si la implementación se ha realizado correctamente o no.

Si ha completado el proceso de incorporación y no ve dispositivos en la [lista Dispositivos](investigate-machines.md) después de una hora, puede comprobar la salida del script en los dispositivos. Para obtener más información, consulte [Solución de problemas de incorporación al implementar con un script](#troubleshoot-onboarding-when-deploying-with-a-script).

Si el script se completa correctamente, consulte [Solución de problemas de incorporación en los dispositivos](#troubleshoot-onboarding-issues-on-the-device) para ver si se producen errores adicionales.

### <a name="troubleshoot-onboarding-issues-when-deploying-with-microsoft-endpoint-configuration-manager"></a>Solución de problemas de incorporación al implementar con Microsoft Endpoint Configuration Manager

Al incorporar dispositivos con las siguientes versiones de Configuration Manager:

- Microsoft Endpoint Configuration Manager
- System Center 2012 Configuration Manager
- Administrador de configuración de System Center 2012 R2

La implementación con las versiones mencionadas anteriormente de Configuration Manager se realiza mediante la ejecución del script de incorporación en los dispositivos. Puede realizar un seguimiento de la implementación en la consola de Configuration Manager.

Si se produce un error en la implementación, puede comprobar la salida del script en los dispositivos.

Si la incorporación se completó correctamente, pero los dispositivos no se muestran en la **lista Dispositivos** después de una hora, consulte [Solución de problemas de incorporación en el dispositivo](#troubleshoot-onboarding-issues-on-the-device) para ver errores adicionales que puedan producirse.

### <a name="troubleshoot-onboarding-when-deploying-with-a-script"></a>Solución de problemas de incorporación al implementar con un script

**Compruebe el resultado del script en el dispositivo:**

1. Haga clic en **Inicio**, escriba **Visor de eventos** y presione **Entrar**.

2. Vaya a Aplicación **de registros** \> **de** Windows.

3. Busque un evento del origen de eventos **WDATPOnboarding** .

Si se produce un error en el script y el evento es un error, puede comprobar el identificador de evento en la tabla siguiente para ayudarle a solucionar el problema.

> [!NOTE]
> Los siguientes identificadores de evento son específicos solo del script de incorporación.

<br>

****

|Id. de evento|Tipo de error|Pasos de resolución|
|:---:|---|---|
|`5`|Se encontraron datos de eliminación, pero no se pudieron eliminar|Compruebe los permisos en el registro, específicamente <p> `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.|
|`10`|Los datos de incorporación no se pudieron escribir en el registro|Compruebe los permisos en el registro, específicamente <p> `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`. <p> Compruebe que el script se ha ejecutado como administrador.|
|`15`|Error al iniciar el servicio SENSE|Compruebe el estado del servicio (`sc query sense` comando). Asegúrese de que no está en un estado intermedio (*'Pending_Stopped'*, *'Pending_Running'*) e intente volver a ejecutar el script (con derechos de administrador). <p> Si el dispositivo ejecuta Windows 10, la versión 1607 y la ejecución del comando `sc query sense` devuelve `START_PENDING`, reinicie el dispositivo. Si el reinicio del dispositivo no soluciona el problema, actualice a KB4015217 e intente volver a incorporarlo.|
|`15`|Error al iniciar el servicio SENSE|Si el mensaje del error es: Error del sistema 577 o error 1058, debe habilitar el controlador ELAM del Antivirus de Microsoft Defender. Para obtener instrucciones, consulte [Asegúrese de que antivirus de Microsoft Defender no está deshabilitado por una directiva](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) .|
|`30`|El script no pudo esperar a que el servicio empezara a ejecutarse.|El servicio podría haber tardado más tiempo en iniciarse o ha encontrado errores al intentar iniciarse. Para obtener más información sobre los eventos y errores relacionados con SENSE, consulte [Revisión de eventos y errores mediante el Visor de eventos](event-error-codes.md).|
|`35`|El script no pudo encontrar el valor necesario del Registro de estado de incorporación|Cuando el servicio SENSE se inicia por primera vez, escribe el estado de incorporación en la ubicación del Registro. <p> `HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`. <p> El script no lo encontró después de varios segundos. Puede probarlo manualmente y comprobar si está allí. Para obtener más información sobre los eventos y errores relacionados con SENSE, consulte [Revisión de eventos y errores mediante el Visor de eventos](event-error-codes.md).|
|`40`|El estado de incorporación del servicio SENSE no está establecido en **1**|El servicio SENSE no se ha incorporado correctamente. Para obtener más información sobre los eventos y errores relacionados con SENSE, consulte [Revisión de eventos y errores mediante el Visor de eventos](event-error-codes.md).|
|`65`|Privilegios insuficientes|Vuelva a ejecutar el script con privilegios de administrador.|
|

### <a name="troubleshoot-onboarding-issues-using-microsoft-intune"></a>Solución de problemas de incorporación mediante Microsoft Intune

Puede usar Microsoft Intune para comprobar los códigos de error e intentar solucionar la causa del problema.

Si ha configurado directivas en Intune y no se propagan en los dispositivos, es posible que tenga que configurar la inscripción automática de MDM.

Use las tablas siguientes para comprender las posibles causas de los problemas durante la incorporación:

- Microsoft Intune códigos de error y OMA-URIs tabla
- Problemas conocidos con la tabla de no cumplimiento
- Tabla de registros de eventos de mobile Administración de dispositivos (MDM)

Si ninguno de los registros de eventos y los pasos de solución de problemas funcionan, descargue el script Local de la sección **Administración** de dispositivos del portal y ejecútelo en un símbolo del sistema con privilegios elevados.

#### <a name="microsoft-intune-error-codes-and-oma-uris"></a>Microsoft Intune códigos de error y OMA-URIs

<br>

****

|Hexadecimal de código de error|Código de error dic|Descripción del error|OMA-URI|Posibles pasos para la causa y solución de problemas|
|:---:|---|---|---|---|
|0x87D1FDE8|-2016281112|Error de corrección|Incorporación <p> Offboarding|**Causa posible:** Error de incorporación o eliminación en un blob incorrecto: firma incorrecta o campos PreviousOrgIds que faltan. <p> **Pasos de solución de problemas:** <p> Compruebe los identificadores de evento en la sección [Ver errores de incorporación del agente en el registro de eventos del dispositivo](#view-agent-onboarding-errors-in-the-device-event-log) . <p> Compruebe los registros de eventos mdm de la tabla siguiente o siga las instrucciones de [Diagnóstico de errores de MDM en Windows](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).|
||||Incorporación <p> Offboarding <p> SampleSharing|**Causa posible:** Microsoft Defender para punto de conexión clave del Registro de directivas no existe o el cliente OMA DM no tiene permisos para escribir en ella. <p> **Pasos de solución de problemas:** Asegúrese de que existe la siguiente clave del Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` <p> Si no existe, abra un comando con privilegios elevados y agregue la clave.|
||||SenseIsRunning <p> OnboardingState <p> OrgId|**Causa posible:** Un intento de corrección por propiedad de solo lectura. Error en la incorporación. <p> **Pasos de solución de problemas:** Consulte los pasos de solución de problemas en [Solución de problemas de incorporación en el dispositivo](#troubleshoot-onboarding-issues-on-the-device). <p> Compruebe los registros de eventos mdm de la tabla siguiente o siga las instrucciones de [Diagnóstico de errores de MDM en Windows](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).|
||||Todo|**Causa posible:** Intente implementar Microsoft Defender para punto de conexión en la SKU o plataforma no admitida, especialmente en la SKU holográfica. <p> Plataformas admitidas actualmente: <p> Enterprise, Education y Professional.<p> No se admite el servidor.|
|0x87D101A9|-2016345687|SyncML(425): error en el comando solicitado porque el remitente no tiene los permisos de control de acceso (ACL) adecuados en el destinatario.|Todo|**Causa posible:** Intente implementar Microsoft Defender para punto de conexión en la SKU o plataforma no admitida, especialmente en la SKU holográfica.<p> Plataformas admitidas actualmente: <p> Enterprise, Education y Professional.|
|

#### <a name="known-issues-with-non-compliance"></a>Problemas conocidos con el incumplimiento

En la tabla siguiente se proporciona información sobre los problemas relacionados con el incumplimiento y cómo se pueden solucionar los problemas.

<br>

****

|Case|Síntomas|Posibles pasos para la causa y solución de problemas|
|:---:|---|---|
|`1`|El dispositivo es compatible con SenseIsRunning OMA-URI. Pero orgId, Onboarding e OnboardingState OMA-URIs no son compatibles.|**Causa posible:** Compruebe que el usuario ha pasado OOBE después de la instalación o actualización de Windows. Durante la incorporación de OOBE no se pudo completar, pero SENSE ya se está ejecutando. <p> **Pasos de solución de problemas:** Espere a que OOBE se complete.|
|`2`|El dispositivo es compatible con OrgId, Onboarding y OnboardingState OMA-URIs, pero SenseIsRunning OMA-URI no es compatible.|**Causa posible:** El tipo de inicio del servicio Sense se establece como "Inicio retrasado". En ocasiones, esto hace que el servidor de Microsoft Intune informe del dispositivo como no compatible con SenseIsRunning cuando se produce una sesión dm al iniciar el sistema. <p> **Pasos de solución de problemas:** El problema debe corregirse automáticamente en un plazo de 24 horas.|
|`3`|El dispositivo no es compatible|**Pasos de solución de problemas:** Asegúrese de que las directivas de incorporación y retirada no se implementen en el mismo dispositivo al mismo tiempo.|
|

#### <a name="mobile-device-management-mdm-event-logs"></a>Registros de eventos de mobile Administración de dispositivos (MDM)

Vea los registros de eventos de MDM para solucionar problemas que pueden surgir durante la incorporación:

Nombre del registro: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider

Nombre del canal: Administración

<br>

****

|Id.|Severity|Descripción del evento|Pasos para la solución de problemas|
|---|---|---|---|
|1819|Error|Microsoft Defender para punto de conexión CSP: no se pudo establecer el valor del nodo. NodeId: (%1), TokenName: (%2), Result: (%3).|Descargue la [actualización acumulativa de Windows 10, 1607](https://go.microsoft.com/fwlink/?linkid=829760).|
|

## <a name="troubleshoot-onboarding-issues-on-the-device"></a>Solución de problemas de incorporación en el dispositivo

Si las herramientas de implementación usadas no indican un error en el proceso de incorporación, pero los dispositivos siguen sin aparecer en la lista de dispositivos en una hora, consulte los siguientes temas de comprobación para comprobar si se produjo un error con el agente de Microsoft Defender para punto de conexión.

- [Visualización de errores de incorporación de agentes en el registro de eventos del dispositivo](#view-agent-onboarding-errors-in-the-device-event-log)
- [Asegúrese de que el servicio de datos de diagnóstico está habilitado](#ensure-the-diagnostics-service-is-enabled)
- [Asegúrese de que el servicio está establecido para iniciarse.](#ensure-the-service-is-set-to-start)
- [Asegurarse de que el dispositivo tiene una conexión a Internet](#ensure-the-device-has-an-internet-connection)
- [Asegúrese de que el Antivirus de Microsoft Defender no está deshabilitado por una directiva](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

### <a name="view-agent-onboarding-errors-in-the-device-event-log"></a>Visualización de errores de incorporación de agentes en el registro de eventos del dispositivo

1. Haga clic en **Inicio**, escriba **Visor de eventos** y presione **Entrar**.

2. En el panel **Visor de eventos (local),** expanda **Registros de aplicaciones y servicios** \> **Microsoft** \> **Windows** \> **SENSE**.

   > [!NOTE]
   > SENSE es un nombre que se usa de forma interna para hacer referencia al sensor de comportamiento que impulsa Microsoft Defender para punto de conexión.

3. Seleccione **Operativo** para cargar el registro.

4. En el panel **Acción** , haga clic en **Filtrar registro actual**.

5. En la pestaña **Filtro** , en **Nivel de evento:** seleccione **Crítico**, **Advertencia** y **Error** y haga clic en **Aceptar**.

   :::image type="content" source="images/filter-log.png" alt-text="Filtro de registro de Visor de eventos" lightbox="images/filter-log.png":::

6. Los eventos que pueden indicar problemas aparecerán en el panel **Operativo** . Puede intentar solucionarlos en función de las soluciones de la tabla siguiente:

   <br>

   ****

   |Identificador de evento|Message|Pasos de resolución|
   |:---:|---|---|
   |`5`|Microsoft Defender para punto de conexión servicio no pudo conectarse al servidor en la _variable_|[Asegúrese de que el dispositivo tiene acceso a Internet](#ensure-the-device-has-an-internet-connection).|
   |`6`|El servicio de Microsoft Defender para punto de conexión no está incorporado y no se han encontrado parámetros de incorporación. Código de error: _variable_|[Vuelva a ejecutar el script de incorporación](configure-endpoints-script.md).|
   |`7`|El servicio de Microsoft Defender para punto de conexión no ha podido leer los parámetros de incorporación. Código de error: _variable_|[Asegúrese de que el dispositivo tiene acceso a Internet](#ensure-the-device-has-an-internet-connection) y vuelva a ejecutar todo el proceso de incorporación.|
   |`9`|El servicio de Microsoft Defender para punto de conexión no ha podido cambiar el tipo de inicio. Código de error: variable|Si el evento se produjo durante la incorporación, reinicie y vuelva a intentar ejecutar el script de incorporación. Para obtener más información, consulte [Ejecutar el script de incorporación de nuevo](configure-endpoints-script.md). <br><br>Si el evento se produjo durante la retirada, póngase en contacto con el soporte técnico.|
   |`10`|El servicio de Microsoft Defender para punto de conexión no ha podido conservar la información de incorporación. Código de error: variable|Si el evento se produjo durante la incorporación, vuelva a intentar ejecutar el script de incorporación. Para obtener más información, consulte [Ejecutar el script de incorporación de nuevo](configure-endpoints-script.md). <br><br>Si el problema persiste, póngase en contacto con el soporte técnico.|
   |`15`|Microsoft Defender para punto de conexión no se puede iniciar el canal de comandos con la dirección URL: _variable_|[Asegúrese de que el dispositivo tiene acceso a Internet](#ensure-the-device-has-an-internet-connection).|
   |`17`|El servicio de Microsoft Defender para punto de conexión no ha podido cambiar la ubicación del servicio Experiencias del usuario y telemetría asociadas. Código de error: variable|[Vuelva a ejecutar el script de incorporación](configure-endpoints-script.md). Si el problema persiste, póngase en contacto con el soporte técnico.|
   |`25`|El servicio de Microsoft Defender para punto de conexión no ha podido restablecer el estado de mantenimiento en el Registro. Código de error: _variable_|Póngase en contacto con el servicio de soporte técnico.|
   |`27`|No se pudo habilitar el modo de Microsoft Defender para punto de conexión en Windows Defender. Error en el proceso de incorporación. Código de error: variable|Póngase en contacto con el servicio de soporte técnico.|
   |`29`|No se han podido leer los parámetros de retirada. Tipo de error: %1, código de error: %2, descripción: %3|Asegúrese de que el dispositivo tiene acceso a Internet y, a continuación, ejecute de nuevo todo el proceso de retirada.|
   |`30`|No se pudo deshabilitar el modo $(build.sense.productDisplayName) en Microsoft Defender para punto de conexión. Código de error: %1|Póngase en contacto con el servicio de soporte técnico.|
   |`32`|El servicio $(build.sense.productDisplayName) no pudo solicitar que se detuviera después del proceso de eliminación. Código de error: %1|Compruebe que el tipo de inicio del servicio es manual y reinicie el dispositivo.|
   |`55`|No se ha podido crear el registrador automático ETW seguro. Código de error: %1|Reinicie el dispositivo.|
   |`63`|Actualizando el tipo de inicio del servicio externo. Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3, código de salida: %4|Identifique lo que está causando cambios en el tipo de inicio del servicio mencionado. Si el código de salida no es 0, corrija manualmente el tipo de inicio al tipo de inicio esperado.|
   |`64`|Inicio del servicio externo detenido. Nombre: %1, código de salida: %2|Póngase en contacto con el soporte técnico si el evento vuelve a aparecer.|
   |`68`|El tipo de inicio del servicio es inesperado. Nombre del servicio: %1, tipo de inicio real: %2, tipo de inicio esperado: %3|Identifique lo que está causando los cambios en el tipo de inicio. Corrección del tipo de inicio de servicio mencionado.|
   |`69`|El servicio se detiene. Nombre del servicio: %1|Inicie el servicio mencionado. Póngase en contacto con el soporte técnico si persiste.|
   |

Hay componentes adicionales en el dispositivo de los que depende el agente de Microsoft Defender para punto de conexión para que funcione correctamente. Si no hay errores relacionados con la incorporación en el registro de eventos del agente de Microsoft Defender para punto de conexión, siga estos pasos para asegurarse de que los componentes adicionales están configurados correctamente.

<span id="ensure-the-diagnostics-service-is-enabled" />

### <a name="ensure-the-diagnostic-data-service-is-enabled"></a>Asegúrese de que el servicio de datos de diagnóstico está habilitado

Si los dispositivos no informan correctamente, es posible que tenga que comprobar que el servicio de datos de diagnóstico de Windows se establece en iniciarse automáticamente y que se está ejecutando en el dispositivo. Es posible que otros programas o cambios de configuración del usuario hayan deshabilitado el servicio.

En primer lugar, debe comprobar que el servicio está configurado para iniciarse automáticamente cuando se inicia Windows, y, a continuación, debe comprobar que el servicio se está ejecutando actualmente (e iniciarlo si no lo está).

### <a name="ensure-the-service-is-set-to-start"></a>Asegúrese de que el servicio está establecido para iniciarse.

**Use la línea de comandos para comprobar el tipo de inicio del servicio de datos de diagnóstico de Windows**:

1. Abra un símbolo del sistema con privilegios elevados en el dispositivo:

   a. Haga clic en **Inicio**, escriba **cmd** y presione **Entrar**.

   b. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```console
   sc qc diagtrack
   ```

   Si el servicio está habilitado, el resultado debe tener un aspecto similar al de la captura de pantalla siguiente:

   :::image type="content" source="images/windefatp-sc-qc-diagtrack.png" alt-text="Resultado del comando de consulta sc para diagtrack" lightbox="images/windefatp-sc-qc-diagtrack.png":::

   `START_TYPE` Si no está establecido en `AUTO_START`, tendrá que establecer el servicio para que se inicie automáticamente.

**Use la línea de comandos para establecer que el servicio de datos de diagnóstico de Windows se inicie automáticamente:**

1. Abra un símbolo del sistema con privilegios elevados en el dispositivo:

   a. Haga clic en **Inicio**, escriba **cmd** y presione **Entrar**.

   b. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```console
   sc config diagtrack start=auto
   ```

3. Se muestra un mensaje correcto. Para comprobar el cambio, escriba el siguiente comando y presione **Entrar**:

   ```console
   sc qc diagtrack
   ```

4. Inicie el servicio. En el símbolo del sistema, escriba el comando siguiente y presione **Entrar**:

   ```console
   sc start diagtrack
   ```

### <a name="ensure-the-device-has-an-internet-connection"></a>Asegurarse de que el dispositivo tiene una conexión a Internet

El sensor de Microsoft Defender para punto de conexión requiere HTTP de Microsoft Windows (WinHTTP) para informar los datos del sensor y comunicarse con el servicio Microsoft Defender para punto de conexión.

WinHTTP es independiente de la configuración del proxy de exploración de Internet y otras aplicaciones de contexto de usuario y debe ser capaz de detectar los servidores proxy que están disponibles en su entorno determinado.

Para asegurarse de que el sensor tiene conectividad de servicio, siga los pasos descritos en el tema [Verify client connectivity to Microsoft Defender para punto de conexión service URL (Comprobar la conectividad de cliente con direcciones URL de servicio de Microsoft Defender para punto de conexión](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)).

Si se produce un error en la comprobación y el entorno usa un proxy para conectarse a Internet, siga los pasos descritos en el tema [Configuración de la configuración de proxy y conectividad a Internet](configure-proxy-internet.md) .

### <a name="ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy"></a>Asegúrese de que el Antivirus de Microsoft Defender no está deshabilitado por una directiva

> [!IMPORTANT]
> Lo siguiente solo se aplica a los dispositivos que aún **no** han recibido la actualización de agosto de 2020 (versión 4.18.2007.8) a Antivirus de Microsoft Defender.
>
> La actualización garantiza que el Antivirus de Microsoft Defender no se puede desactivar en los dispositivos cliente a través de la directiva del sistema.

**Problema**: el servicio Microsoft Defender para punto de conexión no se inicia después de la incorporación.

**Síntoma**: La incorporación se completa correctamente, pero verá el error 577 o el error 1058 al intentar iniciar el servicio.

**Solución**: si los dispositivos ejecutan un cliente antimalware de terceros, el agente de Microsoft Defender para punto de conexión necesita habilitar el controlador Antimalware de inicio anticipado (ELAM). Debe asegurarse de que no está desactivada por una directiva del sistema.

- En función de la herramienta que use para implementar directivas, deberá comprobar que se borran las siguientes directivas de Windows Defender:

  - DisableAntiSpyware
  - DisableAntiVirus

  Por ejemplo, en directiva de grupo no debe haber entradas como los siguientes valores:

  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiSpyware"/></Key>`
  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiVirus"/></Key>`

> [!IMPORTANT]
> La `disableAntiSpyware` configuración se interrumpe y se omitirá en todos los dispositivos Windows 10, a partir de la actualización de agosto de 2020 (versión 4.18.2007.8) a Antivirus de Microsoft Defender.

- Después de borrar la directiva, vuelva a ejecutar los pasos de incorporación.

- También puede comprobar los valores de clave del Registro anteriores para comprobar que la directiva está deshabilitada; para ello, abra la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`del Registro .

  :::image type="content" source="images/atp-disableantispyware-regkey.png" alt-text="La clave del Registro del Antivirus de Microsoft Defender" lightbox="images/atp-disableantispyware-regkey.png":::

   > [!NOTE]
   > Todos los servicios Windows Defender (wdboot, wdfilter, wdnisdrv, wdnissvc y windefend) deben estar en su estado predeterminado. No se admite el cambio del inicio de estos servicios y puede forzarle a volver a crear una imagen del sistema.
   >
   > Configuraciones predeterminadas de ejemplo para WdBoot y WdFilter:
   >
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdBoot"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdFilter"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`

## <a name="troubleshoot-onboarding-issues"></a>Solucionar problemas de incorporación 

> [!NOTE]
> La siguiente guía de solución de problemas solo es aplicable para Windows Server 2016 y versiones inferiores.

Si encuentra problemas al incorporar un servidor, siga los pasos de verificación siguientes para solucionar posibles problemas.


- [Asegúrese de que Microsoft Monitoring Agent (MMA) está instalado y configurado para notificar los datos del sensor al servicio.](configure-server-endpoints.md)
- [Asegúrese de que la configuración del proxy de servidor y la conectividad a Internet están configuradas correctamente](configure-server-endpoints.md)

Es posible que también tenga que comprobar lo siguiente:

- Compruebe que hay un servicio de Microsoft Defender para punto de conexión en ejecución en la pestaña **Procesos** del **Administrador de tareas**. Por ejemplo:

  :::image type="content" source="images/atp-task-manager.png" alt-text="Vista de proceso con Microsoft Defender para punto de conexión Service en ejecución" lightbox="images/atp-task-manager.png":::

- Compruebe **Visor de eventos** \> Administrador de operaciones de registros \> de **aplicaciones y servicios** **para ver** si hay errores.

- En **Servicios**, compruebe si **Microsoft Monitoring Agent** se está ejecutando en el servidor. Por ejemplo,

  :::image type="content" source="images/atp-services.png" alt-text="Los servicios" lightbox="images/atp-services.png":::

- En **Microsoft Monitoring Agent** \> **Azure Log Analytics (OMS),** compruebe las áreas de trabajo y compruebe que el estado se está ejecutando.

  :::image type="content" source="images/atp-mma-properties.png" alt-text="Propiedades del Agente de supervisión de Microsoft" lightbox="images/atp-mma-properties.png":::

- Compruebe que los dispositivos se reflejan en la **lista Dispositivos** del portal.

## <a name="confirming-onboarding-of-newly-built-devices"></a>Confirmación de la incorporación de dispositivos recién creados

Puede haber instancias cuando la incorporación se implemente en un dispositivo recién creado, pero no se haya completado.

Los pasos siguientes proporcionan instrucciones para el escenario siguiente:

- El paquete de incorporación se implementa en dispositivos recién creados
- El sensor no se inicia porque no se ha completado la experiencia rápida (OOBE) o el primer inicio de sesión de usuario
- El dispositivo se apaga o reinicia antes de que el usuario final realice un primer inicio de sesión.
- En este escenario, el servicio SENSE no se iniciará automáticamente aunque se haya implementado el paquete de incorporación.

> [!NOTE]
> El inicio de sesión de usuario después de OOBE ya no es necesario para que el servicio SENSE se inicie en las versiones de Windows siguientes o más recientes: Windows 10, versión 1809 o Windows Server 2019 o Windows Server 2022 con [paquete acumulativo de actualizaciones del 22 de abril de 2021](https://support.microsoft.com/kb/5001384). Windows 10, versión 1909 con [paquete acumulativo de actualizaciones de abril de 2021](https://support.microsoft.com/kb/5001396). Windows 10, versión 2004/20H2 con [paquete acumulativo de actualizaciones del 28 de abril de 2021](https://support.microsoft.com/kb/5001391). 


> [!NOTE]
> Los pasos siguientes solo son pertinentes cuando se usa El punto de conexión de Microsoft Configuration Manager. Para obtener más información sobre la incorporación mediante Configuration Manager de punto de conexión de Microsoft, consulte [Microsoft Defender para punto de conexión](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection).

1. Cree una aplicación en Configuration Manager de punto de conexión de Microsoft.

   :::image type="content" source="images/mecm-1.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-1" lightbox="images/mecm-1.png":::

2. Seleccione **Especificar manualmente la información de la aplicación**.

   :::image type="content" source="images/mecm-2.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-2" lightbox="images/mecm-2.png":::

3. Especifique información sobre la aplicación y, a continuación, seleccione **Siguiente**.

   :::image type="content" source="images/mecm-3.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-3" lightbox="images/mecm-3.png":::

4. Especifique información sobre el centro de software y, a continuación, seleccione **Siguiente**.

   :::image type="content" source="images/mecm-4.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-4" lightbox="images/mecm-4.png":::

5. En **Tipos de implementación** , seleccione **Agregar**.

   :::image type="content" source="images/mecm-5.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-5" lightbox="images/mecm-5.png":::

6. Seleccione **Especificar manualmente la información del tipo de implementación** y, a continuación, seleccione **Siguiente**.

   :::image type="content" source="images/mecm-6.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-6" lightbox="images/mecm-6.png":::

7. Especifique información sobre el tipo de implementación y, a continuación, seleccione **Siguiente**.

   :::image type="content" source="images/mecm-7.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-7" lightbox="images/mecm-7.png":::

8. En Content **Installation program (Programa de instalación** de **contenido**\>), especifique el comando : `net start sense`.

   :::image type="content" source="images/mecm-8.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-8" lightbox="images/mecm-8.png":::

9. En **Método de detección**, seleccione **Configurar reglas para detectar la presencia de este tipo de implementación** y, a continuación, seleccione **Agregar cláusula**.

   :::image type="content" source="images/mecm-9.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-9" lightbox="images/mecm-9.png":::

10. Especifique los siguientes detalles de la regla de detección y, a continuación, seleccione **Aceptar**:

    :::image type="content" source="images/mecm-10.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-10" lightbox="images/mecm-10.png":::

11. En **Método de detección** , seleccione **Siguiente**.

    :::image type="content" source="images/mecm-11.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-11" lightbox="images/mecm-11.png":::

12. En **Experiencia del usuario**, especifique la siguiente información y, a continuación, seleccione **Siguiente**:

    :::image type="content" source="images/mecm-12.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-12" lightbox="images/mecm-12.png":::

13. En **Requisitos**, seleccione **Siguiente**.

    :::image type="content" source="images/mecm-13.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-13" lightbox="images/mecm-13.png":::

14. En **Dependencias**, seleccione **Siguiente**.

    :::image type="content" source="images/mecm-14.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-14" lightbox="images/mecm-14.png":::

15. En **Resumen**, seleccione **Siguiente**.

    :::image type="content" source="images/mecm-15.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-15" lightbox="images/mecm-15.png":::

16. En **Finalización**, seleccione **Cerrar**.

    :::image type="content" source="images/mecm-16.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-16" lightbox="images/mecm-16.png":::

17. En **Tipos de implementación**, seleccione **Siguiente**.

    :::image type="content" source="images/mecm-17.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-17" lightbox="images/mecm-17.png":::

18. En **Resumen**, seleccione **Siguiente**.

    :::image type="content" source="images/mecm-18.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-18" lightbox="images/mecm-18.png":::

    A continuación, se muestra el estado: :::image type="content" source="images/mecm-19.png" alt-text="el punto de conexión de Microsoft Configuration Manager configuration-19" lightbox="images/mecm-19.png":::

19. En **Finalización**, seleccione **Cerrar**.

    :::image type="content" source="images/mecm-20.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-20" lightbox="images/mecm-20.png":::

20. Ahora puede implementar la aplicación haciendo clic con el botón derecho en la aplicación y seleccionando **Implementar**.

    :::image type="content" source="images/mecm-21.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-21" lightbox="images/mecm-21.png":::

21. En **General** , seleccione **Distribuir contenido automáticamente para las dependencias** y **Examinar**.

    :::image type="content" source="images/mecm-22.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-22" lightbox="images/mecm-22.png":::

22. En **Contenido** , seleccione **Siguiente**.

    :::image type="content" source="images/mecm-23.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-23" lightbox="images/mecm-23.png":::

23. En **Configuración de implementación**, seleccione **Siguiente**.

    :::image type="content" source="images/mecm-24.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-24" lightbox="images/mecm-24.png":::

24. En **Programación** , seleccione **Tan pronto como sea posible después de la hora disponible** y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="images/mecm-25.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-25" lightbox="images/mecm-25.png":::

25. En **Experiencia del usuario**, seleccione **Confirmar cambios en la fecha límite o durante una ventana de mantenimiento (requiere reinicios)** y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="images/mecm-26.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-26" lightbox="images/mecm-26.png":::

26. En **Alertas** , seleccione **Siguiente**.

    :::image type="content" source="images/mecm-27.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-27" lightbox="images/mecm-27.png":::

27. En **Resumen**, seleccione **Siguiente**.

    :::image type="content" source="images/mecm-28.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-28" lightbox="images/mecm-28.png":::
      

    A continuación, se muestra :::image type="content" source="images/mecm-29.png" alt-text="el estado El punto de conexión de Microsoft Configuration Manager configuration-29" lightbox="images/mecm-29.png":::

28. En **Finalización**, seleccione **Cerrar**.

    :::image type="content" source="images/mecm-30.png" alt-text="El punto de conexión de Microsoft Configuration Manager configuration-30" lightbox="images/mecm-30.png":::

## <a name="related-topics"></a>Temas relacionados

- [Solucionar problemas de Microsoft Defender para punto de conexión](troubleshoot-mdatp.md)
- [Incorporación de dispositivos](onboard-configure.md)
- [Configurar las opciones de proxy de dispositivo y de conectividad a Internet](configure-proxy-internet.md)
