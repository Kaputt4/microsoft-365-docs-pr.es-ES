---
title: Incorporación Windows dispositivos a Microsoft Defender para endpoint a través de la directiva de grupo
description: Use la directiva de grupo para implementar el paquete de configuración Windows dispositivos para que se incorpore al servicio.
keywords: configurar dispositivos mediante la directiva de grupo, la administración de dispositivos, configurar Microsoft Defender para dispositivos de punto de conexión, incorporar Microsoft Defender para dispositivos de punto de conexión, directiva de grupo
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
ms.date: 12/07/2021
ms.technology: mde
ms.openlocfilehash: 7881a09c0530da09880c0fa1c8c2d73ed0c83000
ms.sourcegitcommit: 726a72f135358603c2fde3f4067d834536e6deb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62327574"
---
# <a name="onboard-windows-devices-using-group-policy"></a>Incorporar dispositivos Windows mediante directiva de grupo 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Se aplica a:**

- Directiva de grupo
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)

> [!NOTE]
> Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debe estar en Windows Server 2008 R2 o posterior.
>
> Para Windows Server 2019 y Windows Server 2022, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.

> [!NOTE]
> Si usa la nueva solución unificada de Microsoft Defender para endpoints para Windows Server 2012 R2 y 2016, asegúrese de usar los archivos ADMX más recientes del almacén central para obtener acceso a las opciones correctas de directiva de Microsoft Defender para puntos de conexión. Consulta [Cómo crear y administrar la Tienda central](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) para plantillas administrativas de directiva de grupo en Windows y descarga los archivos más recientes para usarlos **con Windows 10**.

Consulte el [ARCHIVO PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) [o Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para endpoint.

1. Abra el archivo de paquete de configuración de GP (`WindowsDefenderATPOnboardingPackage.zip`) que descargó del Asistente para incorporación de servicios. También puede obtener el paquete desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender:</a>

    1. En el panel de navegación, **seleccione Configuración** >  **EndpointsDevice** >  **managementOnboarding**  > .

    1. Seleccione el sistema operativo.

    1. En el **campo Método de** implementación, seleccione **Directiva de grupo**.

    1. Haga **clic en Descargar paquete** y guarde el .zip archivo.

2. Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo. Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *WindowsDefenderATPOnboardingScript.cmd*.

3. Para crear un nuevo GPO, abra la Consola de administración de directivas de [grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón secundario en **Objetos** de directiva de grupo que desea configurar y haga clic en **Nuevo**. Escriba el nombre del nuevo GPO en el cuadro de diálogo que se muestra y haga clic en **Aceptar**.

4. Abra la [Consola de administración de directivas de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

5. En el **Editor de administración de directivas de** grupo, vaya a **Configuración del** equipo, preferencias **y, a** continuación, **configuración del panel de control**.

6. Haga clic con el botón secundario en **Tareas programadas**, elija **Nuevo** y, a continuación, haga clic en Tarea **inmediata (al menos Windows 7).**.

7. En la **ventana Tarea** que se abre, vaya a la **pestaña General** . En **Opciones de seguridad,** **haga clic en Cambiar usuario o grupo** y escriba SISTEMA y, a continuación, haga clic **en Comprobar nombres y, a** continuación, **en Aceptar**. NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.

8. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla **Ejecutar con privilegios** más altos.

9. En el campo Nombre, escriba un nombre adecuado para la tarea programada (por ejemplo, Defender for Endpoint Deployment).

10. Vaya a la **pestaña Acciones** y **seleccione Nuevo...** Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción. Escriba la ruta de acceso UNC, con el nombre de dominio completo (FQDN) del servidor de archivos, del archivo *compartido WindowsDefenderATPOnboardingScript.cmd* .

11. Seleccione **Aceptar y** cierre las ventanas GPMC abiertas.

12. Para vincular el GPO a una unidad organizativa (OU), haga clic con el botón secundario y **seleccione Vincular un GPO existente**. En el cuadro de diálogo que se muestra, seleccione el objeto de directiva de grupo que desea vincular. Haga clic en **Aceptar**.

> [!TIP]
> Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que el dispositivo está correctamente incorporado al servicio. Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo defender para endpoint recién incorporado](run-detection-test.md).

## <a name="additional-defender-for-endpoint-configuration-settings"></a>Opciones adicionales de configuración de Defender para puntos de conexión

Para cada dispositivo, puedes especificar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través de Microsoft 365 Defender enviar un archivo para un análisis profundo.

Puede usar la directiva de grupo (GP) para configurar opciones, como las opciones para el uso compartido de muestras usado en la característica de análisis profundo.

### <a name="configure-sample-collection-settings"></a>Configuración de la colección de ejemplo

1. En el dispositivo de administración de GP, copie los siguientes archivos del paquete de configuración:

    - Copiar _AtpConfiguration.admx_ en _C:\\Windows\\ PolicyDefinitions_

    - Copiar _AtpConfiguration.adml_ en _C:\\Windows\\ PolicyDefinitionsen-US\\_

    Si usas un Almacén central para plantillas administrativas de directiva [de grupo](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copia los siguientes archivos del paquete de configuración:

    - Copiar _AtpConfiguration.admx_ en _\\\<forest.root\>\\\\SysVolPoliciesPolicyDefinitions\\\<forest.root\>\\\\_

    - Copiar _AtpConfiguration.adml_ en _\\\<forest.root\>\\\\SysVolPoliciesPolicyDefinitionsen-US\\\<forest.root\>\\\\\\_

2. Abra la [Consola de administración de directivas de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), haga clic con el botón secundario en el GPO que desea configurar y haga clic en **Editar**.

3. En el **Editor de administración de directivas de** grupo, vaya a **Configuración del equipo**.

4. Haga **clic en Directivas** y, a continuación **, en Plantillas administrativas**.

5. Haga **clic Windows componentes y****, a continuación, Windows Defender ATP**.

6. Elige habilitar o deshabilitar el uso compartido de muestras desde tus dispositivos.

> [!NOTE]
> Si no establece un valor, el valor predeterminado es habilitar la colección de muestras.

## <a name="other-recommended-configuration-settings"></a>Otras opciones de configuración recomendadas

### <a name="update-endpoint-protection-configuration"></a>Actualizar la configuración de protección de puntos de conexión

Después de configurar el script de incorporación, siga editando la misma directiva de grupo para agregar configuraciones de protección de extremos. Realice ediciones de directivas de grupo desde un sistema que ejecute Windows 10 o Server 2019, Windows 11 o Windows Server 2022 para asegurarse de que tiene todas las capacidades Antivirus de Microsoft Defender necesarias. Es posible que deba cerrar y volver a abrir el objeto de directiva de grupo para registrar las opciones de configuración de Defender ATP.

Todas las directivas se encuentran en `Computer Configuration\Policies\Administrative Templates`.

**Ubicación de la directiva:** \Windows Components\Windows Defender ATP

Policy|Setting
---|---
Enable\Disable Sample (colección)|Habilitado: "Habilitar la colección de muestras en máquinas" activada

<br>

**Ubicación de la directiva:** \Windows Components\Antivirus de Microsoft Defender

Policy|Setting
---|---
Configurar la detección para aplicaciones potencialmente no deseadas|Enabled, Block

<br>

**Ubicación de la directiva:** \Windows Components\Antivirus de Microsoft Defender\MAPS

Policy|Setting
---|---
Unirse a Microsoft MAPS|Mapas avanzados habilitados
Enviar ejemplos de archivos cuando sea necesario realizar análisis adicionales | Habilitado, Enviar muestras seguras

<br>

**Ubicación de la directiva:** \Windows Components\Antivirus de Microsoft Defender\Real-time Protection

Policy|Setting
---|---
Desactivar la protección en tiempo real|Deshabilitado
Activar la supervisión del comportamiento|Habilitado
Examinar todos los archivos y datos adjuntos descargados|Habilitado
Supervisar la actividad de archivos y programas en el equipo|Habilitado

<br>

**Ubicación de la directiva:** \Windows Components\Antivirus de Microsoft Defender\Scan

Estas opciones configuran exámenes periódicos del extremo. Se recomienda realizar un examen rápido semanal, lo que permite el rendimiento.

Policy|Setting
---|---
Compruebe la inteligencia de seguridad de virus y spyware más reciente antes de ejecutar un examen programado |Habilitado

<br>

**Ubicación de la directiva:** \Windows Components\Antivirus de Microsoft Defender\Protección contra vulnerabilidades de seguridad de Microsoft Defender\Attack Surface Reduction

Obtén la lista actual de GUID de reglas de reducción de superficie de ataque de la fase 3 de implementación de reglas de reducción de superficie [de ataque: implementar](attack-surface-reduction-rules-deployment-implement.md). Para obtener más información sobre las reglas, consulta [Referencia de reglas de reducción de superficie de ataque](attack-surface-reduction-rules-reference.md)

1. Abre la **directiva Configurar reducción de superficie de ataque** .

1. Seleccione **Habilitado**.

1. Seleccione el **botón Mostrar** .

1. Agregue cada GUID en el **campo Nombre de** valor con un valor de 2.

   Esto configurará cada uno solo para auditoría.

   ![Imagen de configuración de reducción de superficie de ataque.](images/asr-guid.png)

Policy|Ubicación|Setting
---|---|---
Configurar acceso controlado a carpetas| \Windows Components\Antivirus de Microsoft Defender\Protección contra vulnerabilidades de seguridad de Microsoft Defender\Controlled Folder Access| Habilitado, modo auditoría

## <a name="run-a-detection-test-to-verify-onboarding"></a>Ejecutar una prueba de detección para comprobar la incorporación

Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio. Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado](run-detection-test.md).

## <a name="offboard-devices-using-group-policy"></a>Dispositivos offboard con directiva de grupo

Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se te notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.

1. Obtenga el paquete de offboarding del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender web</a>:

    1. En el panel de navegación, **seleccione Configuración** >  **EndpointsDevice** >  **managementOffboarding** > .

    1. Seleccione el sistema operativo.
    
    1. En el **campo Método de** implementación, seleccione **Directiva de grupo**.

    1. Haga **clic en Descargar paquete** y guarde el .zip archivo.

2. Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo. Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Abra la [Consola de administración de directivas de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

4. En el **Editor de administración de directivas de** grupo, vaya a **Configuración del equipo, preferencias** **y, a** continuación, **configuración del panel de control**.

5. Haga clic con el **botón secundario en Tareas programadas**, **elija Nuevo** y, a continuación, haga clic **en Tarea inmediata**.

6. En la **ventana Tarea** que se abre, vaya a la **pestaña General** . Elija la cuenta de usuario del SISTEMA local (BUILTIN\SYSTEM) en **Opciones de seguridad**.

7. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.

8. En el campo Nombre, escriba un nombre adecuado para la tarea programada (por ejemplo, Defender for Endpoint Deployment).

9. Vaya a la **pestaña Acciones** y **seleccione Nuevo...**. Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción. Escriba la ruta de acceso UNC, con el nombre de dominio completo (FQDN) del servidor de archivos, del archivo *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* .

10. Seleccione **Aceptar y** cierre las ventanas GPMC abiertas.

> [!IMPORTANT]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.

## <a name="monitor-device-configuration"></a>Supervisar la configuración del dispositivo

Con la directiva de grupo no hay una opción para supervisar la implementación de directivas en los dispositivos. La supervisión se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

## <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos con el portal

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal Microsoft 365 Defender web</a>.
2. Haga clic **en Inventario de dispositivos**.
3. Compruebe que aparecen dispositivos.

> [!NOTE]
> Los dispositivos pueden tardar varios días en aparecer en la **lista dispositivos**. Esto incluye el tiempo que tardan las directivas en distribuirse en el dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en iniciar la presentación de informes.

## <a name="setup-defender-av-policies"></a>Directivas antivirus de Setup Defender

Crea una nueva directiva de grupo o agrupa esta configuración con las otras directivas. Esto depende del entorno de los clientes y de cómo les gustaría realizar el servicio al dirigirse a diferentes unidades organizativas (UNIDADES organizativas).

1. Después de elegir el GP o crear uno nuevo, edite el GP.

2. Vaya a **Configuración del** >  **equipoPoliciesAdministrative** >  **Templates** >  **Windows Components** >  **Antivirus de Microsoft Defender** >  **Real-time Protection**.

    :::image type="content" source="images/realtime-protect.png" alt-text="protección en tiempo real.":::

1. En la carpeta Cuarentena, configure la eliminación de elementos de la carpeta Cuarentena.

    :::image type="content" source="images/removal-items-quarantine1.png" alt-text="carpeta de cuarentena de elementos de eliminación.":::

    :::image type="content" source="images/config-removal-items-quarantine2.png" alt-text="cuarentena de eliminación de config.":::

4. En la carpeta Examinar, configure las opciones de examen.

    :::image type="content" source="images/gpo-scans.png" alt-text="análisis de gpo.":::

### <a name="monitor-all-files-in-real-time-protection"></a>Supervisar todos los archivos en protección en tiempo real

Vaya a **Directivas de configuración del** \>  \> equipo **Plantillas** \> **administrativas Windows componentes Antivirus de Microsoft Defender** \>  \> **protección en tiempo real**.

 Dado que el valor de "Examinar archivos entrantes y salientes" (predeterminado) es 0, la directiva de grupo de "Configurar la supervisión de la actividad de programa y archivo entrante y saliente" para la configuración "bidireccional (acceso completo)" cambia a deshabilitada.

:::image type="content" source="images/config-monitor-incoming-outgoing-file-act.png" alt-text="configurar la supervisión de la actividad de archivos salientes entrantes.":::

### <a name="configure-windows-defender-smartscreen-settings"></a>Configurar Windows Defender smartscreen

1. Vaya a **Directivas de configuración del** \>  \> equipo **Plantillas** \> **administrativas Windows componentes Windows Defender** \> **SmartScreen** \> **Explorer**.

    :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="config explorador de pantalla inteligente de Windows Defender.":::
 
2. Vaya a **Configuración del** >  **equipoPoliciesAdministrative** >  **Templates** >  **Windows Components** >  **Windows Defender SmartScreen** >  **Microsoft Edge**.

    :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="config Windows Defender smart screen Edge.":::

### <a name="configure-potentially-unwanted-applications"></a>Configurar aplicaciones potencialmente no deseadas

Vaya a **Directivas de configuración del** \>  \> equipo **Plantillas** \> **administrativas Windows componentes Antivirus de Microsoft Defender**\>.

:::image type="content" source="images/config-potential-unwanted-apps.png" alt-text="config posible aplicación no deseada.":::

:::image type="content" source="images/config-potential-unwanted-apps2.png" alt-text="potencial de configuración.":::

### <a name="configure-cloud-deliver-protection-and-send-samples-automatically"></a>Configurar la protección de entrega en la nube y enviar muestras automáticamente

Vaya a **Directivas de configuración del** \>  \> equipo **Plantillas** \> **administrativas Windows componentes Antivirus de Microsoft Defender** \>  \> **MAPS**.

:::image type="content" source="images/gpo-maps1.png" alt-text="mapas.":::

:::image type="content" source="images/gpo-maps-block-atfirst-sight.png" alt-text="bloque a primera vista.":::

:::image type="content" source="images/gpo-maps-join-ms-maps.png" alt-text="unirse a mapas de Microsoft.":::

:::image type="content" source="images/send-file-sample-further-analysis-require.png" alt-text="enviar ejemplo de archivo cuando sea necesario realizar un análisis adicional.":::

### <a name="check-for-signature-update"></a>Buscar la actualización de firmas

Vaya a **Directivas de configuración del** \>  \> equipo **Plantillas** \> **administrativas Windows componentes Antivirus de Microsoft Defender** \> actualizaciones **de** \> **inteligencia de seguridad**.

:::image type="content" source="images/signature-update-1.png" alt-text="actualización de firma.":::

:::image type="content" source="images/signature-update-2.png" alt-text="actualización de definición de firma.":::

### <a name="configure-cloud-deliver-timeout-and-protection-level"></a>Configurar el tiempo de espera de entrega en la nube y el nivel de protección

Vaya a **Directivas de configuración del** \>  \> equipo **Plantillas** \> **administrativas Windows componentes Antivirus de Microsoft Defender** \>  \> **MpEngine**.
Al configurar la directiva de nivel de protección en la nube en **Default Antivirus de Microsoft Defender blocking policy**, se deshabilitará la directiva. Esto es lo que se necesita para establecer el nivel de protección en el valor predeterminado de Windows.

:::image type="content" source="images/config-extended-cloud-check.png" alt-text="comprobación de nube extendida de config.":::

:::image type="content" source="images/cloud-protection-level.png" alt-text="nivel de protección de la nube config.":::

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows mediante Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows mediante herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows mediante un script local](configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en un Microsoft Defender recién incorporado para dispositivos de punto de conexión](run-detection-test.md)
- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](troubleshoot-onboarding.md)
