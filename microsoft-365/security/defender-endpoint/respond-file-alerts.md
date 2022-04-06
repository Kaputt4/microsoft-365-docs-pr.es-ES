---
title: Realizar acciones de respuesta en un archivo de Microsoft Defender para punto de conexión
description: Realice acciones de respuesta en alertas relacionadas con archivos al detener y poner en cuarentena un archivo o bloquear un archivo y comprobar los detalles de la actividad.
keywords: respond, stop and quarantine, block file, deep analysis
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8bfa08a92a011d32cdc30e2f68052715b4075fdf
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665522"
---
# <a name="take-response-actions-on-a-file"></a>Realizar acciones de respuesta en un archivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Desea experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-responddile-abovefoldlink)

Responda rápidamente a los ataques detectados mediante la detención y la cuarentena de archivos o el bloqueo de un archivo. Después de realizar acciones en los archivos, puede comprobar los detalles de la actividad en el Centro de acciones.

Las acciones de respuesta están disponibles en la página de perfil detallada de un archivo. Una vez en esta página, puede cambiar entre los diseños de página nuevo y antiguo si cambia la **nueva página Archivo**. En el resto de este artículo se describe el diseño de página más reciente.

Las acciones de respuesta se ejecutan en la parte superior de la página de archivos e incluyen:

- Detener y poner en cuarentena el archivo
- Agregar indicador
- Descargar archivo
- Consultar a un experto en amenazas
- Centro de actividades

También puede enviar archivos para un análisis profundo para ejecutar el archivo en un espacio aislado de nube seguro. Una vez completado el análisis, obtendrá un informe detallado que proporciona información sobre el comportamiento del archivo. Para enviar archivos para un análisis profundo y leer informes anteriores, seleccione la pestaña **Análisis profundo** . Se encuentra debajo de las tarjetas de información del archivo.

Algunas acciones requieren ciertos permisos. En la tabla siguiente se describe qué acción pueden realizar determinados permisos en archivos ejecutables portátiles (PE) y no PE:

|Permiso|Archivos PE|Archivos que no son pe|
|---|:---:|:---:|
|Ver datos|X|X|
|Investigación de alertas|&#x2611;|X|
|Respuesta dinámica básica|X|X|
|Respuesta dinámica avanzada|&#x2611;|&#x2611;|

Para obtener más información sobre los roles, consulte [Creación y administración de roles para el control de acceso basado en rol](user-roles.md).

## <a name="stop-and-quarantine-files-in-your-network"></a>Detener y poner en cuarentena archivos de la red

Puede contener un ataque en su organización si detiene el proceso malintencionado y anula el archivo donde se observó.

> [!IMPORTANT]
> Solo puede realizar esta acción si:
>
> - El dispositivo en el que va a realizar la acción se ejecuta Windows 10, versión 1703 o posterior y Windows 11
> - El archivo no pertenece a editores de terceros de confianza o no está firmado por Microsoft
> - Antivirus de Microsoft Defender debe ejecutarse al menos en modo pasivo. Para obtener más información, consulte [compatibilidad Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).

La acción **Detener y poner en cuarentena el archivo** incluye detener los procesos en ejecución, poner en cuarentena los archivos y eliminar datos persistentes, como claves del Registro.

Esta acción surte efecto en dispositivos con Windows 10, versión 1703 o posterior y Windows 11, donde se observó el archivo en los últimos 30 días.

> [!NOTE]
> Podrá restaurar el archivo desde la cuarentena en cualquier momento.

### <a name="stop-and-quarantine-files"></a>Detener y poner en cuarentena los archivos

1. Seleccione el archivo que desea detener y poner en cuarentena. Puede seleccionar un archivo de cualquiera de las vistas siguientes o usar el cuadro De búsqueda:

   - **Alertas** : haga clic en los vínculos correspondientes de la descripción o los detalles de la escala de tiempo del artículo de alertas.
   - **Cuadro de búsqueda** : seleccione **Archivo** en el menú desplegable y escriba el nombre de archivo.

   > [!NOTE]
   > La acción detener y poner en cuarentena el archivo está limitada a un máximo de 1000 dispositivos. Para detener un archivo en un número mayor de dispositivos, consulte [Agregar indicador para bloquear o permitir el archivo](#add-indicator-to-block-or-allow-a-file).

2. Vaya a la barra superior y seleccione **Detener y poner en cuarentena el archivo**.

   :::image type="content" source="images/atp-stop-quarantine-file.png" alt-text="Acción detener y poner en cuarentena el archivo" lightbox="images/atp-stop-quarantine-file.png":::

3. Especifique un motivo y, a continuación, seleccione **Confirmar**.

   :::image type="content" source="images/atp-stop-quarantine.png" alt-text="Página del archivo de detención y cuarentena" lightbox="images/atp-stop-quarantine.png":::

   El Centro de acciones muestra la información de envío:

   :::image type="content" source="images/atp-stopnquarantine-file.png" alt-text="Centro de acciones para detener y poner en cuarentena el archivo" lightbox="images/atp-stopnquarantine-file.png":::

   - **Tiempo de envío** : muestra cuándo se envió la acción.
   - **Correcto** : muestra el número de dispositivos en los que el archivo se ha detenido y puesto en cuarentena.
   - **Error** : muestra el número de dispositivos en los que se produjo un error en la acción y los detalles sobre el error.
   - **Pendiente** : muestra el número de dispositivos desde los que aún no se ha detenido y puesto en cuarentena el archivo. Esto puede tardar tiempo en casos en los que el dispositivo está sin conexión o no está conectado a la red.

4. Seleccione cualquiera de los indicadores de estado para ver más información sobre la acción. Por ejemplo, seleccione **No se pudo** ver dónde se produjo un error en la acción.

#### <a name="notification-on-device-userf"></a>Notificación en userf del dispositivo

Cuando se quita el archivo de un dispositivo, se muestra la siguiente notificación:

:::image type="content" source="images/atp-notification-file.png" alt-text="La notificación a en el usuario del dispositivo" lightbox="images/atp-notification-file.png":::

En la escala de tiempo del dispositivo, se agrega un nuevo evento para cada dispositivo donde se detuvo y puso en cuarentena un archivo.

Se muestra una advertencia antes de que se implemente la acción para los archivos ampliamente usados en toda una organización. Es para validar que la operación está pensada.

## <a name="restore-file-from-quarantine"></a>Restaurar archivo de la cuarentena

Puede revertir y quitar un archivo de la cuarentena si ha determinado que está limpio después de una investigación. Ejecute el siguiente comando en cada dispositivo en el que se puso en cuarentena el archivo.

1. Abra un símbolo del sistema con privilegios elevados en el dispositivo:

   1. Vaya a **Inicio** y escriba _cmd_.

   1. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```dos
   "%ProgramFiles%\Windows Defender\MpCmdRun.exe" -Restore -Name EUS:Win32/CustomEnterpriseBlock -All
   ```

   > [!NOTE]
   > En algunos escenarios, **ThreatName** puede aparecer como: EUS:Win32/CustomEnterpriseBlock!cl.
   >
   > Defender para punto de conexión restaurará todos los archivos bloqueados personalizados que se pusieron en cuarentena en este dispositivo en los últimos 30 días.

> [!IMPORTANT]
> Es posible que un archivo que se puso en cuarentena como una posible amenaza de red no se pueda recuperar. Si un usuario intenta restaurar el archivo después de la cuarentena, es posible que no sea accesible. Esto puede deberse a que el sistema ya no tiene credenciales de red para acceder al archivo. Normalmente, esto es el resultado de un inicio de sesión temporal en un sistema o carpeta compartida y los tokens de acceso han expirado.

## <a name="download-or-collect-file"></a>Descargar o copiar archivos

Al seleccionar **Descargar archivo** de las acciones de respuesta, puede descargar un archivo de .zip local protegido con contraseña que contenga el archivo. Aparecerá un control flotante donde puede registrar un motivo para descargar el archivo y establecer una contraseña.

De forma predeterminada, debería poder descargar los archivos que están en cuarentena.

:::image type="content" source="images/atp-download-file-action.png" alt-text="Acción de descarga del archivo" lightbox="images/atp-download-file-action.png":::

### <a name="download-quarantined-files"></a>Descarga de archivos en cuarentena

Los archivos que Antivirus de Microsoft Defender o el equipo de seguridad han puesto en cuarentena se guardarán de forma compatible según [las configuraciones de envío de ejemplo](enable-cloud-protection-microsoft-defender-antivirus.md). El equipo de seguridad puede descargar los archivos directamente desde la página de detalles del archivo mediante el botón "Descargar archivo". **Esta característica de vista previa está activada de forma predeterminada**.

La ubicación depende de la configuración geográfica de su organización (UE, Reino Unido o EE. UU.). Un archivo en cuarentena solo se recopilará una vez por organización. Obtenga más información sobre la protección de datos de Microsoft desde el Portal de confianza de servicios en https://aka.ms/STP.

Tener esta configuración activada puede ayudar a los equipos de seguridad a examinar archivos potencialmente incorrectos e investigar incidentes rápidamente y de una manera menos arriesgada. Sin embargo, si necesita desactivar esta configuración, vaya a **Configuración** \> **Características** \> **avanzadas de puntos** \> de conexión **Descargar archivos en cuarentena** para ajustar la configuración. [Más información sobre las características avanzadas](advanced-features.md)

#### <a name="backing-up-quarantined-files"></a>Copia de seguridad de archivos en cuarentena

Es posible que se pida a los usuarios que proporcionen consentimiento explícito antes de realizar una copia de seguridad del archivo en cuarentena, en función de la [configuración de envío de ejemplo](enable-cloud-protection-microsoft-defender-antivirus.md#use-group-policy-to-turn-on-cloud-protection).

Esta característica no funcionará si el envío de ejemplo está desactivado. Si el envío de ejemplo automático está establecido para solicitar permiso al usuario, solo se recopilarán los ejemplos que el usuario acepte enviar.

> [!IMPORTANT]
> Descargue los requisitos de archivo en cuarentena:
>
> - La organización usa Antivirus de Microsoft Defender en modo activo
> - La versión del motor antivirus es 1.1.17300.4 o posterior. Consulte [Versiones mensuales de la plataforma y del motor](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)
> - La protección basada en la nube está habilitada. Consulte [Activación de la protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)
> - El envío de ejemplo está activado
> - Los dispositivos tienen Windows 10 versión 1703 o posterior, o Windows servidor 2016 o 2019, o Windows Server 2022 o Windows 11

### <a name="collect-files"></a>Recopilar archivos

Si Microsoft Defender para punto de conexión no almacena un archivo, no puede descargarlo. En su lugar, verá un botón **Recopilar archivo** en la misma ubicación. Si no se ha visto un archivo en la organización en los últimos 30 días, se deshabilitará **Recopilar archivo** .
> [!Important]
> Es posible que un archivo que se puso en cuarentena como una posible amenaza de red no se pueda recuperar. Si un usuario intenta restaurar el archivo después de la cuarentena, es posible que no sea accesible. Esto puede deberse a que el sistema ya no tiene credenciales de red para acceder al archivo. Normalmente, esto es el resultado de un inicio de sesión temporal en un sistema o carpeta compartida y los tokens de acceso han expirado.

## <a name="add-indicator-to-block-or-allow-a-file"></a>Agregar indicador para bloquear o permitir un archivo

Evite la propagación de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o sospechas de malware. Si conoce un archivo ejecutable portátil (PE) potencialmente malintencionado, puede bloquearlo. Esta operación impedirá que se lea, escriba o ejecute en dispositivos de su organización.

> [!IMPORTANT]
>
> - Esta característica está disponible si su organización usa Antivirus de Microsoft Defender y la protección entregada en la nube está habilitada. Para obtener más información, consulte [Administración de la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
>
> - La versión de cliente de Antimalware debe ser 4.18.1901.x o posterior.
> - Esta característica está diseñada para evitar que se descargue malware sospechoso (o archivos potencialmente malintencionados) desde la web. Actualmente admite archivos ejecutables portátiles (PE), _incluidos archivos.exe_ y _.dll_ . La cobertura se ampliará con el tiempo.
> - Esta acción de respuesta está disponible para dispositivos en Windows 10, versión 1703 o posterior y Windows 11.
> - La función allow o block no se puede realizar en los archivos si la clasificación del archivo existe en la memoria caché del dispositivo antes de la acción de permitir o bloquear.

> [!NOTE]
> El archivo PE debe estar en la escala de tiempo del dispositivo para poder realizar esta acción.
>
> Puede haber un par de minutos de latencia entre el momento en que se realiza la acción y el archivo real bloqueado.

### <a name="enable-the-block-file-feature"></a>Habilitación de la característica de archivo de bloque

Para empezar a bloquear archivos, primero debe [activar la característica **Bloquear o permitir**](advanced-features.md) en Configuración.

### <a name="allow-or-block-file"></a>Permitir o bloquear el archivo

Al agregar un hash de indicador para un archivo, puede optar por generar una alerta y bloquear el archivo cada vez que un dispositivo de su organización intente ejecutarlo.

Los archivos bloqueados automáticamente por un indicador no se mostrarán en el Centro de acciones del archivo, pero las alertas seguirán siendo visibles en la cola Alertas.

Consulte [Administrar indicadores](manage-indicators.md) para obtener más información sobre cómo bloquear y generar alertas en los archivos.

Para detener el bloqueo de un archivo, quite el indicador. Puede hacerlo a través de la acción **Editar indicador** en la página de perfil del archivo. Esta acción será visible en la misma posición que la acción **Agregar indicador** , antes de agregar el indicador.

También puede editar indicadores desde la página **Configuración**, en **Indicadores** de **reglas**\>. Los indicadores aparecen en esta área por el hash de su archivo.

## <a name="consult-a-threat-expert"></a>Consultar a un experto en amenazas

Consulte a un experto en amenazas de Microsoft para obtener más información sobre un dispositivo potencialmente comprometido o dispositivos ya en peligro. Expertos en amenazas de Microsoft se contratan directamente desde el portal de Microsoft 365 Defender para obtener una respuesta oportuna y precisa. Los expertos proporcionan información sobre un dispositivo potencialmente comprometido y le ayudan a comprender las amenazas complejas y las notificaciones de ataque dirigidas. También pueden proporcionar información sobre las alertas o un contexto de inteligencia sobre amenazas que vea en el panel del portal.

Consulte [Consulta con un experto en amenazas de Microsoft](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) para obtener más información.

## <a name="check-activity-details-in-action-center"></a>Comprobar los detalles de actividad en el Centro de actividades

El **Centro de acciones** proporciona información sobre las acciones que se realizaron en un dispositivo o archivo. Puede ver los detalles siguientes:

- Colección de paquetes de investigación
- Examen antivirus
- Restricción de la aplicación
- Aislamiento del dispositivo

También se muestran todos los demás detalles relacionados, como la fecha y hora de envío, el usuario que envía y si la acción se realizó correctamente o no.

:::image type="content" source="images/action-center-details.png" alt-text="Centro de acciones con información" lightbox="images/action-center-details.png":::

## <a name="deep-analysis"></a>Análisis detallado

Las investigaciones de ciberseguridad suelen desencadenarse mediante una alerta. Las alertas están relacionadas con uno o varios archivos observados que a menudo son nuevos o desconocidos. La selección de un archivo le lleva a la vista de archivos donde puede ver los metadatos del archivo. Para enriquecer los datos relacionados con el archivo, puede enviar el archivo para un análisis profundo.

La característica análisis profundo ejecuta un archivo en un entorno de nube seguro y totalmente instrumentado. Los resultados de análisis detallados muestran las actividades del archivo, los comportamientos observados y los artefactos asociados, como archivos eliminados, modificaciones del Registro y comunicación con direcciones IP.
El análisis profundo admite actualmente un amplio análisis de archivos ejecutables portátiles (PE) ( _incluidos los archivos.exe_ y _.dll_ ).

El análisis profundo de un archivo tarda varios minutos. Una vez completado el análisis de archivos, la pestaña Análisis profundo se actualizará para mostrar un resumen y la fecha y hora de los últimos resultados disponibles.

El resumen de análisis detallado incluye una lista de *comportamientos observados*, algunos de los cuales pueden indicar actividad malintencionada y *observables*, incluidas las direcciones IP y los archivos creados en el disco. Si no se encontró nada, estas secciones mostrarán un breve mensaje.

Los resultados del análisis profundo se comparan con la inteligencia sobre amenazas y las coincidencias generarán las alertas adecuadas.

Use la característica de análisis profundo para investigar los detalles de cualquier archivo, normalmente durante una investigación de una alerta o por cualquier otro motivo en el que sospeche un comportamiento malintencionado. Esta característica está disponible en la pestaña **Análisis profundo** , en la página de perfil del archivo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4aAYy?rel=0]

**Enviar para un análisis profundo** está habilitado cuando el archivo está disponible en la colección de ejemplo de back-end de Defender para punto de conexión, o si se observó en un dispositivo Windows 10 que admite el envío a análisis profundos.

> [!NOTE]
> Solo los archivos de Windows 10 y Windows 11 se pueden recopilar automáticamente.

También puede enviar un ejemplo a través del [portal de Microsoft 365 Defender](https://www.microsoft.com/security/portal/submission/submit.aspx) si el archivo no se observó en un dispositivo Windows 10 (o Windows 11) y esperar a que el botón **Enviar análisis profundo** esté disponible.

> [!NOTE]
> Debido a los flujos de procesamiento de back-end en el portal de Microsoft 365 Defender, podría haber hasta 10 minutos de latencia entre el envío de archivos y la disponibilidad de la característica de análisis profundo en Defender para punto de conexión.

### <a name="submit-files-for-deep-analysis"></a>Envío de archivos para un análisis profundo

1. Seleccione el archivo que desea enviar para un análisis profundo. Puede seleccionar o buscar un archivo en cualquiera de las vistas siguientes:

    - **Alertas** : seleccione los vínculos de archivo **en descripción o** **detalles** en la escala de tiempo del artículo de alertas.
    - **Lista dispositivos**: seleccione los vínculos de archivo en la sección **Descripción** o **Detalles** de la sección **Dispositivo de la organización**
    - **Cuadro de búsqueda** : seleccione **Archivo** en el menú desplegable y escriba el nombre de archivo.

2. En la pestaña **Análisis profundo** de la vista de archivos, seleccione **Enviar**.

   :::image type="content" source="images/submit-file.png" alt-text="Botón Enviar archivos PE" lightbox="images/submit-file.png":::

   > [!NOTE]
   > Solo se admiten archivos PE, incluidos _los archivos.exe_ y _.dll_ .

   Se muestra una barra de progreso y proporciona información sobre las distintas fases del análisis. A continuación, puede ver el informe cuando se realice el análisis.

> [!NOTE]
> En función de la disponibilidad del dispositivo, el tiempo de recopilación de muestras puede variar. Hay un tiempo de espera de 3 horas para la recopilación de ejemplos. Se producirá un error en la recopilación y la operación se anulará si no hay informes en línea Windows 10 dispositivo (o Windows 11) en ese momento. Puede volver a enviar archivos para un análisis profundo para obtener datos nuevos en el archivo.

### <a name="view-deep-analysis-reports"></a>Visualización de informes de análisis detallados

Vea el informe de análisis detallado proporcionado para ver información más detallada sobre el archivo que envió. Esta característica está disponible en el contexto de la vista de archivos.

Puede ver el informe completo que proporciona detalles sobre las secciones siguientes:

- Behaviors
- Observables

Los detalles proporcionados pueden ayudarle a investigar si hay indicios de un posible ataque.

1. Seleccione el archivo que envió para un análisis profundo.
2. Seleccione la pestaña **Análisis profundo** . Si hay informes anteriores, el resumen del informe aparecerá en esta pestaña.

   :::image type="content" source="images/analysis-results-nothing500.png" alt-text="El informe de análisis detallado que muestra información detallada en varias categorías" lightbox="images/analysis-results-nothing500.png":::

#### <a name="troubleshoot-deep-analysis"></a>Solución de problemas de análisis profundo

Si se encuentra con un problema al intentar enviar un archivo, pruebe cada uno de los pasos de solución de problemas siguientes.

1. Asegúrese de que el archivo en cuestión es un archivo PE. Los archivos PE suelen tener extensiones _de.exe_ o _.dll_ (aplicaciones o programas ejecutables).

2. Asegúrese de que el servicio tiene acceso al archivo, de que sigue existiendo y de que no se ha dañado ni modificado.

3. Espere un poco e intente volver a enviar el archivo. La cola puede estar llena o ha habido un error de conexión o comunicación temporal.

4. Si la directiva de recopilación de ejemplo no está configurada, el comportamiento predeterminado es permitir la recopilación de ejemplo. Si está configurado, compruebe que la configuración de directiva permite la recopilación de ejemplo antes de volver a enviar el archivo. Cuando se configure la colección de ejemplo, compruebe el siguiente valor del Registro:

    ```text
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 - block sample collection
      Value = 1 - allow sample collection
    ```

5. Cambie la unidad organizativa a través de la directiva de grupo. Para obtener más información, vea [Configurar con directiva de grupo](configure-endpoints-gp.md).

6. Si estos pasos no resuelven el problema, póngase en contacto con el soporte técnico.

## <a name="related-topics"></a>Temas relacionados

- [Realizar acciones de respuesta en un dispositivo](respond-machine-alerts.md)
- [Investigar archivos](investigate-files.md)
- [Acciones de respuesta manual en Microsoft Defender para punto de conexión Plan 1](defender-endpoint-plan-1.md#manual-response-actions)
