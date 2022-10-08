---
title: Incorporación de dispositivos Windows para Microsoft Defender para punto de conexión a través de directiva de grupo
description: Use directiva de grupo para implementar el paquete de configuración en dispositivos Windows para que se incorporen al servicio.
keywords: configurar dispositivos mediante la directiva de grupo, la administración de dispositivos, la configuración de dispositivos Microsoft Defender para punto de conexión, la incorporación de dispositivos Microsoft Defender para punto de conexión, la directiva de grupo
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.date: 12/07/2021
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 3aa8872609f07e9382c9b7e2040a417a99221c63
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68180525"
---
# <a name="onboard-windows-devices-using-group-policy"></a>Incorporar dispositivos Windows mediante directiva de grupo 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Se aplica a:**

- Directiva de grupo
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)

> [!NOTE]
> Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debe estar en Windows Server 2008 R2 o posterior.
>
> Para Windows Server 2019 y Windows Server 2022, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.

> [!NOTE]
> Si usa la nueva solución de Microsoft Defender para punto de conexión unificada para Windows Server 2012 R2 y 2016, asegúrese de que usa los archivos ADMX más recientes de la tienda central para obtener acceso a la correcta. Microsoft Defender para punto de conexión opciones de directiva. Consulta [Cómo crear y administrar la Tienda Central para plantillas administrativas de directiva de grupo en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) y descarga los archivos más recientes **para usarlos con Windows 10**.

Consulte el [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)  o  [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para punto de conexión.

1. Abra el archivo de paquete de configuración de GP (`WindowsDefenderATPOnboardingPackage.zip`) que descargó del Asistente para incorporación de servicios. También puede obtener el paquete desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>:

    1. En el panel de navegación, seleccione **Configuración** > **Puntos de conexión** > **Incorporación** **de administración de**  >  dispositivos.

    1. Seleccione el sistema operativo.

    1. En el campo **Método de implementación** , seleccione **Directiva de grupo**.

    1. Haga clic en **Descargar paquete** y guarde el archivo .zip.

2. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda acceder el dispositivo. Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *WindowsDefenderATPOnboardingScript.cmd*.

3. Para crear un nuevo GPO, abra la [consola de administración de directiva de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón derecho en **directiva de grupo Objetos** que desea configurar y haga clic en **Nuevo**. Escriba el nombre del nuevo GPO en el cuadro de diálogo que se muestra y haga clic en **Aceptar**.

4. Abra la [consola de administración de directiva de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón derecho en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

5. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo**, **Preferencias** y, a continuación, **Configuración del panel de control**.

6. Haga clic con el botón derecho en **Tareas programadas**, seleccione **Nuevo** y, a continuación, haga clic en **Tarea inmediata (al menos Windows 7).**

7. En la ventana **Tarea** que se abre, vaya a la pestaña **General** . En **Opciones de seguridad** , haga clic en **Cambiar usuario o grupo** y escriba SYSTEM y, a continuación, haga clic en **Comprobar nombres** y, a continuación, **en Aceptar**. NT AUTHORITY\SYSTEM aparece como la cuenta de usuario como se ejecutará la tarea.

8. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla **Ejecutar con los privilegios más altos** .

9. En el campo Nombre, escriba un nombre adecuado para la tarea programada (por ejemplo, Implementación de Defender para punto de conexión).

10. Vaya a la pestaña **Acciones** y seleccione **Nuevo...** Asegúrese de que **Iniciar un programa** está seleccionado en el campo **Acción** . Escriba la ruta de acceso UNC, con el nombre de dominio completo (FQDN) del servidor de archivos del archivo *WindowsDefenderATPOnboardingScript.cmd* compartido.

11. Seleccione **Aceptar** y cierre las ventanas de GPMC abiertas.

12. Para vincular el GPO a una unidad organizativa (OU), haga clic con el botón derecho y seleccione **Vincular un GPO existente**. En el cuadro de diálogo que se muestra, seleccione el objeto directiva de grupo que desea vincular. Haga clic en **Aceptar**.

> [!TIP]
> Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que el dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un dispositivo De Defender para punto de conexión recién incorporado](run-detection-test.md).

## <a name="additional-defender-for-endpoint-configuration-settings"></a>Opciones de configuración adicionales de Defender para punto de conexión

Para cada dispositivo, puede indicar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través de Microsoft 365 Defender para enviar un archivo para un análisis profundo.

Puede usar directiva de grupo (GP) para configurar opciones, como la configuración del uso compartido de ejemplo que se usa en la característica de análisis profundo.

### <a name="configure-sample-collection-settings"></a>Configuración de la colección de ejemplo

1. En el dispositivo de administración de GP, copie los siguientes archivos del paquete de configuración:

    - Copiar _AtpConfiguration.admx_ en _C:\\Windows\\PolicyDefinitions_

    - Copia _de AtpConfiguration.adml_ en _C:\\Windows\\PolicyDefinitions\\en-US_

    Si usa una [tienda central para directiva de grupo plantillas administrativas](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copie los siguientes archivos del paquete de configuración:

    - Copiar _AtpConfiguration.admx_ en _\\\<forest.root\>\\\\directivas sysvolDefinitions\\\<forest.root\>\\\\_

    - Copiar _AtpConfiguration.adml_ en _\\\\\\\<forest.root\>directivas sysvolDefinitions\\\\\<forest.root\>\\\\en-US_

2. Abra la [consola de administración de directiva de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), haga clic con el botón derecho en el GPO que desea configurar y haga clic en **Editar**.

3. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo**.

4. Haga clic en **Directivas** y, a continuación, **en Plantillas administrativas**.

5. Haga clic en **Componentes de Windows** y, a continuación, **Windows Defender ATP**.

6. Elija habilitar o deshabilitar el uso compartido de ejemplos desde los dispositivos.

> [!NOTE]
> Si no establece un valor, el valor predeterminado es habilitar la colección de ejemplo.

## <a name="other-recommended-configuration-settings"></a>Otras opciones de configuración recomendadas

### <a name="update-endpoint-protection-configuration"></a>Actualización de la configuración de Endpoint Protection

Después de configurar el script de incorporación, siga editando la misma directiva de grupo para agregar configuraciones de endpoint protection. Realice modificaciones de directivas de grupo desde un sistema que ejecute Windows 10, Server 2019, Windows 11 o Windows Server 2022 para asegurarse de que tiene todas las funcionalidades necesarias Microsoft Defender Antivirus. Es posible que tenga que cerrar y volver a abrir el objeto de directiva de grupo para registrar la configuración de ATP de Defender.

Todas las directivas se encuentran en `Computer Configuration\Policies\Administrative Templates`.

**Ubicación de directiva:** \Componentes de Windows\Windows Defender ATP

Policy|Setting
---|---
Enable\Disable Sample collection|Habilitado: activada la opción "Habilitar recopilación de ejemplos en máquinas"

<br>

**Ubicación de directiva:** \Componentes de Windows\Microsoft Defender Antivirus

Policy|Setting
---|---
Configuración de la detección para aplicaciones potencialmente no deseadas|Habilitado, Bloquear

<br>

**Ubicación de directiva:** \Componentes de Windows\Microsoft Defender Antivirus\MAPS

Policy|Setting
---|---
Unirse a Microsoft MAPS|Habilitado, Mapas avanzados
Envío de ejemplos de archivos cuando se requiera un análisis adicional | Habilitado, Enviar ejemplos seguros

<br>

**Ubicación de directiva:** \Componentes de Windows\Microsoft Defender Antivirus\Protección en tiempo real

Policy|Setting
---|---
Desactivar la protección en tiempo real|Deshabilitada
Activar la supervisión del comportamiento|Habilitado
Examinar todos los archivos y datos adjuntos descargados|Habilitado
Supervisión de la actividad de archivos y programas en el equipo|Habilitado

<br>

**Ubicación de directiva:** \Componentes de Windows\Microsoft Defender Antivirus\Scan

Esta configuración configura exámenes periódicos del punto de conexión. Se recomienda realizar un examen rápido semanal, lo que permite el rendimiento.

Policy|Setting
---|---
Comprobación de la inteligencia de seguridad de virus y spyware más reciente antes de ejecutar un examen programado |Habilitado

<br>

**Ubicación de la directiva:** \Componentes de Windows\Microsoft Defender Antivirus\Microsoft Defender Protección contra vulnerabilidades de seguridad\Reducción de superficie expuesta a ataques

Obtenga la lista actual de reglas de reducción de superficie expuesta a ataques GUID de la [implementación de reglas de reducción de superficie expuesta a ataques Paso 3: Implementar reglas ASR](attack-surface-reduction-rules-deployment-implement.md). Para obtener más detalles, por reglas, consulte [Referencia de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md).

1. Abra la directiva **Configurar reducción de superficie expuesta a ataques** .

1. Seleccione **Habilitado**.

1. Seleccione el botón **Mostrar** .

1. Agregue cada GUID en el campo **Nombre de valor** con un valor de 2.

   Esto configurará cada uno solo para la auditoría.

   :::image type="content" source="images/asr-guid.png" alt-text="Configuración de reducción de superficie expuesta a ataques" lightbox="images/asr-guid.png":::

Policy|Ubicación|Setting
---|---|---
Configuración del acceso controlado a carpetas| \Componentes de Windows\Microsoft Defender Antivirus\Microsoft Defender Protección contra vulnerabilidades de seguridad\Acceso controlado a carpetas| Habilitado, Modo de auditoría

## <a name="run-a-detection-test-to-verify-onboarding"></a>Ejecución de una prueba de detección para comprobar la incorporación

Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que un dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md).

## <a name="offboard-devices-using-group-policy"></a>Dispositivos fuera del panel que usan directiva de grupo

Por motivos de seguridad, el paquete usado para dispositivos Offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones imprevisibles.

1. Obtenga el paquete de offboarding desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>:

    1. En el panel de navegación, seleccione **Configuración** > **Puntos de conexión** >  Administración **de** > **dispositivos Offboarding**.

    1. Seleccione el sistema operativo.
    
    1. En el campo **Método de implementación** , seleccione **Directiva de grupo**.

    1. Haga clic en **Descargar paquete** y guarde el archivo .zip.

2. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda acceder el dispositivo. Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Abra la [consola de administración de directiva de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón derecho en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

4. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo,** **Preferencias** y, a continuación, **Configuración del panel de control**.

5. Haga clic con el botón derecho en **Tareas programadas**, seleccione **Nuevo** y, a continuación, haga clic en **Tarea inmediata**.

6. En la ventana **Tarea** que se abre, vaya a la pestaña **General** . Elija la cuenta de usuario de SYSTEM local (BUILTIN\SYSTEM) en **Opciones de seguridad**.

7. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla **Ejecutar con los privilegios más altos** .

8. En el campo Nombre, escriba un nombre adecuado para la tarea programada (por ejemplo, Implementación de Defender para punto de conexión).

9. Vaya a la pestaña **Acciones** y seleccione **Nuevo...**. Asegúrese de que **Iniciar un programa** está seleccionado en el campo **Acción** . Escriba la ruta de acceso UNC, con el nombre de dominio completo (FQDN) del servidor de archivos, del archivo *compartido WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* .

10. Seleccione **Aceptar** y cierre las ventanas de GPMC abiertas.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.

## <a name="monitor-device-configuration"></a>Supervisión de la configuración del dispositivo

Con directiva de grupo no hay una opción para supervisar la implementación de directivas en los dispositivos. La supervisión se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

## <a name="monitor-devices-using-the-portal"></a>Supervisión de dispositivos mediante el portal

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.
2. Haga clic en **Inventario de dispositivos**.
3. Compruebe que aparecen los dispositivos.

> [!NOTE]
> Los dispositivos pueden tardar varios días en aparecer en la **lista Dispositivos**. Esto incluye el tiempo que tardan las directivas en distribuirse al dispositivo, el tiempo que tarda el usuario en iniciar sesión y el tiempo que tarda el punto de conexión en iniciar la generación de informes.

## <a name="setup-defender-av-policies"></a>Configuración de directivas de Antivirus de Defender

Cree un nuevo directiva de grupo o agrupe esta configuración con las demás directivas. Esto depende del entorno del cliente y de cómo le gustaría implementar el servicio dirigiendo las unidades organizativas (OU) diferentes.

1. Después de elegir el GP o crear uno nuevo, edite el GP.

2. Vaya a **Directivas** >  **de configuración** >  del equipo **Plantillas** >  administrativas **Componentes** >  de Windows **Microsoft Defender Antivirus** > **Protección en tiempo real**.

    :::image type="content" source="images/realtime-protect.png" alt-text="Protección en tiempo real" lightbox="images/realtime-protect.png":::

1. En la carpeta Cuarentena, configure la eliminación de elementos de la carpeta Cuarentena.

    :::image type="content" source="images/removal-items-quarantine1.png" alt-text="Carpeta de cuarentena de elementos de eliminación" lightbox="images/removal-items-quarantine1.png":::

    :::image type="content" source="images/config-removal-items-quarantine2.png" alt-text="cuarentena de eliminación de configuración" lightbox="images/config-removal-items-quarantine2.png":::

4. En la carpeta Examinar, configure los valores de examen.

    :::image type="content" source="images/gpo-scans.png" alt-text="exámenes de gpo" lightbox="images/gpo-scans.png":::

### <a name="monitor-all-files-in-real-time-protection"></a>Supervisión de todos los archivos en la protección en tiempo real

Vaya a **Directivas** \> **de configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> **de Windows Microsoft Defender Antivirus** \> **Protección en tiempo real**.

:::image type="content" source="images/config-monitor-incoming-outgoing-file-act.png" alt-text="Configuración de la supervisión de la actividad de archivo saliente entrante" lightbox="images/config-monitor-incoming-outgoing-file-act.png":::

### <a name="configure-windows-defender-smartscreen-settings"></a>Configuración de Windows Defender SmartScreen

1. Vaya a **Directivas** \> **de configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> de Windows Windows Defender **Explorador** **de SmartScreen**\>.

   :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="Configuración del Explorador de pantalla inteligente de Windows Defender" lightbox="images/config-windows-def-smartscr-explorer.png":::
 
2. Vaya a **Directivas** >  **de configuración** >  del equipo **Plantillas** >  administrativas **Componentes** >  **de Windows Windows Defender SmartScreen** > **Microsoft Edge**.

    :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="Configuración de Edge de pantalla inteligente de Windows Defender" lightbox="images/config-windows-def-smartscr-explorer.png":::

### <a name="configure-potentially-unwanted-applications"></a>Configuración de aplicaciones potencialmente no deseadas

Vaya a **Directivas** \> **de configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> **de Windows Microsoft Defender Antivirus**.

:::image type="content" source="images/config-potential-unwanted-apps.png" alt-text="Configuración de una posible aplicación no deseada" lightbox="images/config-potential-unwanted-apps.png":::

:::image type="content" source="images/config-potential-unwanted-apps2.png" alt-text="potencial de configuración" lightbox="images/config-potential-unwanted-apps2.png":::

### <a name="configure-cloud-deliver-protection-and-send-samples-automatically"></a>Configuración de Cloud Deliver Protection y envío automático de ejemplos

Vaya a **Directivas** \> **de configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> **de Windows Microsoft Defender Antivirus** \> **MAPS**.

:::image type="content" source="images/gpo-maps1.png" alt-text="Mapas" lightbox="images/gpo-maps1.png":::

:::image type="content" source="images/gpo-maps-block-atfirst-sight.png" alt-text="Bloqueo a primera vista" lightbox="images/gpo-maps-block-atfirst-sight.png":::

:::image type="content" source="images/gpo-maps-join-ms-maps.png" alt-text="Unirse a microsoft maps" lightbox="images/gpo-maps-join-ms-maps.png":::

:::image type="content" source="images/send-file-sample-further-analysis-require.png" alt-text="Enviar ejemplo de archivo cuando se requiera un análisis adicional" lightbox="images/send-file-sample-further-analysis-require.png":::

> [!NOTE]
> La opción **Enviar todos los ejemplos** proporcionará la mayor parte del análisis de archivos binarios, scripts o documentos, lo que aumenta la posición de seguridad.
La opción **Enviar ejemplos seguros** limita el tipo de archivos binarios, scripts o documentos que se están analizando y reduce la posición de seguridad. 

Para obtener más información, consulte [Activar la protección en la nube en Microsoft Defender Antivirus](enable-cloud-protection-microsoft-defender-antivirus.md) y [Protección en la nube y envío de ejemplo en Microsoft Defender Antivirus.](cloud-protection-microsoft-antivirus-sample-submission.md)

### <a name="check-for-signature-update"></a>Comprobación de la actualización de firma

Vaya a **Directivas** \> **de configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> de Windows **Microsoft Defender Antivirus** \> **Security Intelligence Novedades**.

:::image type="content" source="images/signature-update-1.png" alt-text="Actualización de firma" lightbox="images/signature-update-1.png":::

:::image type="content" source="images/signature-update-2.png" alt-text="Actualización de la definición de firma" lightbox="images/signature-update-2.png":::

### <a name="configure-cloud-deliver-timeout-and-protection-level"></a>Configuración del tiempo de espera y el nivel de protección de entrega en la nube

Vaya a **Directivas** \> **de configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> **de Windows Microsoft Defender Antivirus** \> **MpEngine**.
Al configurar la directiva de nivel de protección en la nube en **Predeterminada Microsoft Defender directiva de bloqueo antivirus**, se deshabilitará la directiva. Esto es lo que se necesita para establecer el nivel de protección en el valor predeterminado de Windows.

:::image type="content" source="images/config-extended-cloud-check.png" alt-text="comprobación de la nube extendida de config" lightbox="images/config-extended-cloud-check.png":::

:::image type="content" source="images/cloud-protection-level.png" alt-text="nivel de protección en la nube de configuración" lightbox="images/cloud-protection-level.png":::

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows mediante Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows mediante herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows mediante un script local](configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)
- [Ejecución de una prueba de detección en dispositivos Microsoft Defender para punto de conexión recién incorporados](run-detection-test.md)
- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
