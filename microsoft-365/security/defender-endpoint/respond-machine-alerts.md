---
title: Realizar acciones de respuesta en un dispositivo en Microsoft Defender para punto de conexión
description: Realice acciones de respuesta en un dispositivo, como aislar dispositivos, recopilar un paquete de investigación, administrar etiquetas, ejecutar un examen av y restringir la ejecución de la aplicación.
keywords: respond, isolate, isolate device, collect investigation package, action center, restrict, manage tags, av scan, restrict app
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: f09ec3f00ff7076d4e76a1b32804eb5e43f5e557
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621503"
---
# <a name="take-response-actions-on-a-device"></a>Realizar acciones de respuesta en un dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión, planes 1 y 2](defender-endpoint-plan-1-2.md)
- [Microsoft Defender para Empresas](/microsoft-365/security/defender-business/mdb-overview)

[!INCLUDE [Prerelease information](../../includes/prerelease.md)]

Responda rápidamente a los ataques detectados mediante el aislamiento de dispositivos o la recopilación de un paquete de investigación. Después de realizar acciones en los dispositivos, puede comprobar los detalles de la actividad en el Centro de acciones.

Las acciones de respuesta se ejecutan en la parte superior de una página de dispositivo específica e incluyen:

- Administrar etiquetas
- Iniciar investigación automatizada
- Iniciar sesión de respuesta dinámica
- Recopilar el paquete de investigación
- Ejecutar examen de antivirus
- Restringir ejecución de aplicación
- Aislar el dispositivo
- Contener dispositivo
- Consultar a un experto en amenazas
- Centro de actividades

[![Imagen de las acciones de respuesta.](images/response-actions.png)](images/response-actions.png#lightbox)

> [!IMPORTANT]
> El plan 1 y [Microsoft Defender para Empresas](../defender-business/mdb-overview.md) de [Defender para punto de conexión](defender-endpoint-plan-1.md) incluyen solo las siguientes acciones de respuesta manual:
> - Ejecutar examen de antivirus
> - Aislar el dispositivo
> - Detener y poner en cuarentena un archivo
> - Agregue un indicador para bloquear o permitir un archivo La suscripción debe incluir el plan 2 de Defender para punto de conexión para tener todas las acciones de respuesta descritas en este artículo.

 Puede encontrar páginas de dispositivo desde cualquiera de las vistas siguientes:

- **Cola de alertas**: seleccione el nombre del dispositivo junto al icono de dispositivo en la cola de alertas.
- **Lista de dispositivos** : seleccione el encabezado del nombre del dispositivo en la lista de dispositivos.
- **Cuadro de búsqueda**: seleccione Dispositivo en el menú desplegable y escriba el nombre del dispositivo.

> [!IMPORTANT]
> - Estas acciones de respuesta solo están disponibles para dispositivos en Windows 10, versión 1703 o posterior, Windows 11, Windows Server 2019 y Windows Server 2022.
> - En el caso de las plataformas que no son de Windows, las funcionalidades de respuesta (como el aislamiento de dispositivos) dependen de las funcionalidades de terceros.
> - Para los agentes de primera entidad de Microsoft, consulte el vínculo "más información" de cada característica para conocer los requisitos mínimos del sistema operativo.

## <a name="manage-tags"></a>Administrar etiquetas

Agregue o administre etiquetas para crear una afiliación de grupo lógico. Las etiquetas de dispositivo son compatibles con la asignación adecuada de la red, lo que permite adjuntar diferentes etiquetas para capturar contexto y habilitar la creación de listas dinámicas como parte de un incidente.

Para obtener más información sobre el etiquetado de dispositivos, consulte [Creación y administración de etiquetas de dispositivo](machine-tags.md).

## <a name="initiate-automated-investigation"></a>Iniciar investigación automatizada

Puede iniciar una nueva investigación automatizada de uso general en el dispositivo si es necesario. Mientras se ejecuta una investigación, cualquier otra alerta generada desde el dispositivo se agregará a una investigación automatizada en curso hasta que se complete esa investigación. Además, si se ve la misma amenaza en otros dispositivos, esos dispositivos se agregan a la investigación.

Para obtener más información sobre las investigaciones automatizadas, consulte [Introducción a las investigaciones automatizadas](automated-investigations.md).

## <a name="initiate-live-response-session"></a>Iniciar sesión de respuesta en directo

La respuesta en vivo es una funcionalidad que proporciona acceso instantáneo a un dispositivo mediante una conexión de shell remoto. Esto le ofrece la capacidad de realizar un trabajo de investigación en profundidad y tomar medidas de respuesta inmediatas para contener rápidamente amenazas identificadas en tiempo real.

La respuesta en directo está diseñada para mejorar las investigaciones, ya que le permite recopilar datos forenses, ejecutar scripts, enviar entidades sospechosas para su análisis, corregir amenazas y buscar amenazas emergentes de forma proactiva.

Para obtener más información sobre la respuesta en vivo, consulte [Investigación de entidades en dispositivos que usan la respuesta en vivo](live-response.md).

## <a name="collect-investigation-package-from-devices"></a>Recopilación de paquetes de investigación de dispositivos

Como parte del proceso de investigación o respuesta, puede recopilar un paquete de investigación de un dispositivo. Al recopilar el paquete de investigación, puede identificar el estado actual del dispositivo y comprender aún más las herramientas y técnicas usadas por el atacante.

> [!IMPORTANT]
> Estas acciones no se admiten actualmente para dispositivos que ejecutan macOS o Linux. Use la respuesta activa para ejecutar la acción. Para obtener más información sobre la respuesta en vivo, consulte [Investigación de entidades en dispositivos con respuesta dinámica](live-response.md).

Para descargar el paquete (archivo Zip) e investigar los eventos que se produjeron en un dispositivo

1. Seleccione **Recopilar paquete de investigación** en la fila de acciones de respuesta en la parte superior de la página del dispositivo.

2. Especifique en el cuadro de texto por qué desea realizar esta acción. Seleccione **Confirmar**.

3. El archivo zip se descargará

Forma alternativa:

1. Seleccione **Centro de acciones** en la sección acciones de respuesta de la página del dispositivo.

   :::image type="content" source="images/action-center-package-collection.png" alt-text="La opción Centro de acciones" lightbox="images/action-center-package-collection.png":::

2. En el control flotante del Centro de acciones, seleccione **Paquete de colección de paquetes disponible** para descargar el archivo ZIP.

   :::image type="content" source="images/collect-package.png" alt-text="Opción del paquete de descarga" lightbox="images/collect-package.png":::

El paquete contiene las siguientes carpetas:

|Folder|Descripción|
|---|---|
|Autoruns|Contiene un conjunto de archivos que representan el contenido del registro de un punto de entrada de inicio automático (ASEP) conocido para ayudar a identificar la persistencia del atacante en el dispositivo. <p> <div class="alert"><b>NOTA:</b> Si no se encuentra la clave del Registro, el archivo contendrá el siguiente mensaje: "ERROR: El sistema no pudo encontrar la clave o el valor del Registro especificados".<div>|
|Programas instalados|Este archivo .CSV contiene la lista de programas instalados que pueden ayudar a identificar lo que está instalado actualmente en el dispositivo. Para obtener más información, vea [Win32_Product clase](https://go.microsoft.com/fwlink/?linkid=841509).|
|Conexiones de red|Esta carpeta contiene un conjunto de puntos de datos relacionados con la información de conectividad que puede ayudar a identificar la conectividad con direcciones URL sospechosas, la infraestructura de comandos y control del atacante (C&C), cualquier movimiento lateral o conexiones remotas. <ul><li>ActiveNetConnections.txt: muestra las estadísticas de protocolo y las conexiones de red TCP/IP actuales. Proporciona la capacidad de buscar conectividad sospechosa realizada por un proceso.</li><li>Arp.txt: muestra las tablas de caché del protocolo de resolución de direcciones (ARP) actuales para todas las interfaces. La caché arp puede revelar otros hosts en una red que se han visto comprometidos o sistemas sospechosos en la red que podrían haberse usado para ejecutar un ataque interno.</il><li>DnsCache.txt: muestra el contenido de la caché del solucionador de cliente DNS, que incluye ambas entradas precargadas desde el archivo hosts local y los registros de recursos obtenidos recientemente para las consultas de nombres resueltas por el equipo. Esto puede ayudar a identificar conexiones sospechosas.</li><li>IpConfig.txt: muestra la configuración completa de TCP/IP para todos los adaptadores. Los adaptadores pueden representar interfaces físicas, como adaptadores de red instalados o interfaces lógicas, como conexiones de acceso telefónico local.</li><li>FirewallExecutionLog.txt y pfirewall.log</li></ul><p><div class="alert"><b>NOTA:</b> El archivo pfirewall.log debe existir en %windir%\system32\logfiles\firewall\pfirewall.log, por lo que se incluirá en el paquete de investigación. Para obtener más información sobre cómo crear el archivo de registro de firewall, consulte [Configuración del firewall de Windows डिफेन्डर con registro de seguridad avanzada](/windows/security/threat-protection/windows-firewall/configure-the-windows-firewall-log).<div>|
|Archivos de captura previa|Los archivos de captura previa de Windows están diseñados para acelerar el proceso de inicio de la aplicación. Se puede usar para realizar un seguimiento de todos los archivos usados recientemente en el sistema y buscar seguimientos de aplicaciones que podrían haberse eliminado, pero que todavía se pueden encontrar en la lista de archivos de captura previa. <ul><li>Carpeta de captura previa: contiene una copia de los archivos de captura previa de `%SystemRoot%\Prefetch`. NOTA: Se recomienda descargar un visor de archivos de captura previa para ver los archivos de captura previa.</li><li>PrefetchFilesList.txt: contiene la lista de todos los archivos copiados que se pueden usar para realizar un seguimiento de si se produjo algún error de copia en la carpeta de captura previa.</li></ul>|
|Procesos|Contiene un archivo .CSV que enumera los procesos en ejecución y proporciona la capacidad de identificar los procesos actuales que se ejecutan en el dispositivo. Esto puede ser útil al identificar un proceso sospechoso y su estado.|
|Tareas programadas|Contiene un archivo .CSV que enumera las tareas programadas, que se pueden usar para identificar las rutinas realizadas automáticamente en un dispositivo elegido para buscar código sospechoso que se estableció para ejecutarse automáticamente.|
|Registro de eventos de seguridad|Contiene el registro de eventos de seguridad, que contiene registros de actividad de inicio de sesión o cierre de sesión, u otros eventos relacionados con la seguridad especificados por la directiva de auditoría del sistema. <p><div class="alert"><b>NOTA:</b> Abra el archivo de registro de eventos mediante el Visor de eventos.</div>|
|Servicios|Contiene un archivo .CSV que enumera los servicios y sus estados.|
|Sesiones de bloque de mensajes de Windows Server (SMB)|Enumera el acceso compartido a archivos, impresoras y puertos serie y las comunicaciones varias entre nodos de una red. Esto puede ayudar a identificar la filtración de datos o el movimiento lateral. <p> Contiene archivos para SMBInboundSessions y SMBOutboundSession. <p> <div class="alert"><b>NOTA:</b> Si no hay sesiones (entrantes o salientes), obtendrá un archivo de texto que le indicará que no se han encontrado sesiones SMB.</div>|
|Información del sistema|Contiene un archivo SystemInformation.txt que muestra información del sistema, como la versión del sistema operativo y las tarjetas de red.|
|Directorios temporales|Contiene un conjunto de archivos de texto que enumera los archivos ubicados en %Temp% para cada usuario del sistema. <p> Esto puede ayudar a realizar un seguimiento de los archivos sospechosos que un atacante puede haber eliminado en el sistema. <p> <div class="alert"><b>NOTA:</b> Si el archivo contiene el siguiente mensaje: "El sistema no encuentra la ruta de acceso especificada", significa que no hay ningún directorio temporal para este usuario y podría deberse a que el usuario no ha iniciar sesión en el sistema.</div>|
|Usuarios y grupos|Proporciona una lista de archivos que representan cada uno de ellos un grupo y sus miembros.|
|WdSupportLogs|Proporciona los MpCmdRunLog.txt y MPSupportFiles.cab  <p> <div class="alert"><b>NOTA:</b> Esta carpeta solo se creará en Windows 10, versión 1709 o posterior con paquete acumulativo de actualizaciones de febrero de 2020 o instalado más reciente: <ul><li>Win10 1709 (RS3) Compilación 16299.1717: [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</li><li>Win10 1803 (RS4) Compilación 17134.1345: [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</li><li>Win10 1809 (RS5) Compilación 17763.1075: [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</li><li>Win10 1903/1909 (19h1/19h2) Compilaciones 18362.693 y 18363.693: [KB4535996](https://support.microsoft.com/help/4535996/windows-10-update-kb4535996)</li></ul> </div>|
|CollectionSummaryReport.xls|Este archivo es un resumen de la colección de paquetes de investigación, contiene la lista de puntos de datos, el comando usado para extraer los datos, el estado de ejecución y el código de error si se produce un error. Puede usar este informe para realizar un seguimiento de si el paquete incluye todos los datos esperados e identificar si se han producido errores.|
|

## <a name="run-microsoft-defender-antivirus-scan-on-devices"></a>Ejecución Microsoft Defender examen del Antivirus en dispositivos

Como parte del proceso de investigación o respuesta, puede iniciar de forma remota un examen antivirus para ayudar a identificar y corregir el malware que podría estar presente en un dispositivo en peligro.

> [!IMPORTANT]
> - Esta acción no se admite actualmente para macOS y Linux. Use la respuesta activa para ejecutar la acción. Para obtener más información sobre la respuesta en vivo, consulte [Investigación de entidades en dispositivos con respuesta dinámica](live-response.md).
> - Un examen Microsoft Defender Antivirus puede ejecutarse junto con otras soluciones antivirus, tanto si Microsoft Defender Antivirus es la solución antivirus activa como si no. Microsoft Defender Antivirus puede estar en modo pasivo. Para obtener más información, consulte [compatibilidad con Microsoft Defender Antivirus](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-compatibility).

Una vez que haya seleccionado **Ejecutar examen antivirus**, seleccione el tipo de examen que desea ejecutar (rápido o completo) y agregue un comentario antes de confirmar el examen.

:::image type="content" source="images/run-antivirus.png" alt-text="Notificación para seleccionar examen rápido o examen completo y agregar comentario" lightbox="images/run-antivirus.png":::

El Centro de acciones mostrará la información de examen y la escala de tiempo del dispositivo incluirá un nuevo evento, lo que refleja que se envió una acción de examen en el dispositivo. Microsoft Defender alertas antivirus reflejarán las detecciones que aparecen durante el examen.

> [!NOTE]
> Al desencadenar un examen mediante la acción de respuesta de Defender para punto de conexión, Microsoft Defender valor del antivirus "ScanAvgCPULoadFactor" sigue aplicando y limita el impacto de la CPU del examen.
> Si ScanAvgCPULoadFactor no está configurado, el valor predeterminado es un límite del 50 % de carga máxima de CPU durante un examen.
> Para obtener más información, consulte [configure-advanced-scan-types-microsoft-defender-antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/configure-advanced-scan-types-microsoft-defender-antivirus).

## <a name="restrict-app-execution"></a>Restringir ejecución de aplicación

Además de contener un ataque mediante la detención de procesos malintencionados, también puede bloquear un dispositivo e impedir que se ejecuten intentos posteriores de programas potencialmente malintencionados.

> [!IMPORTANT]
> - Esta acción está disponible para dispositivos en Windows 10, versión 1709 o posterior, Windows 11 y Windows Server 2019 o posterior. 
> - Esta característica está disponible si su organización usa Microsoft Defender Antivirus.
> - Esta acción debe cumplir los requisitos de firma y formatos de directiva de integridad de código Windows डिफेन्डर Application Control. Para obtener más información, vea [Formatos de directivas de integridad de código y firma](/windows/security/threat-protection/windows-defender-application-control/use-code-signing-to-simplify-application-control-for-classic-windows-applications)).

Para impedir que una aplicación se ejecute, se aplica una directiva de integridad de código que solo permite que los archivos se ejecuten si están firmados por un certificado emitido por Microsoft. Este método de restricción puede ayudar a evitar que un atacante controle dispositivos en peligro y realice otras actividades malintencionadas.

> [!NOTE]
> Podrá revertir la restricción de que las aplicaciones se ejecuten en cualquier momento. El botón de la página del dispositivo cambiará para decir **Quitar restricciones de aplicación** y, a continuación, realizará los mismos pasos que restringir la ejecución de la aplicación.

Una vez que haya seleccionado **Restringir la ejecución** de la aplicación en la página del dispositivo, escriba un comentario y seleccione **Confirmar**. El Centro de acciones mostrará la información del examen y la escala de tiempo del dispositivo incluirá un nuevo evento.

:::image type="content" source="images/restrict-app-execution.png" alt-text="Notificación de restricción de la aplicación" lightbox="images/restrict-app-execution.png":::

### <a name="notification-on-device-user"></a>Notificación al usuario del dispositivo

Cuando una aplicación está restringida, se muestra la siguiente notificación para informar al usuario de que se está limitando la ejecución de una aplicación:

:::image type="content" source="images/atp-app-restriction.png" alt-text="Mensaje de restricción de la aplicación" lightbox="images/atp-app-restriction.png":::

> [!NOTE]
> La notificación no está disponible en Windows Server 2016 y Windows Server 2012 R2.

## <a name="isolate-devices-from-the-network"></a>Aislar dispositivos de la red

En función de la gravedad del ataque y de la confidencialidad del dispositivo, es posible que desee aislar el dispositivo de la red. Esta acción puede ayudar a evitar que el atacante controle el dispositivo en peligro y realice otras actividades, como la filtración de datos y el movimiento lateral.

> [!IMPORTANT]
> - Actualmente no se admite el aislamiento de dispositivos de la red para dispositivos que ejecutan macOS o Linux. Para macOS, use la respuesta en directo para ejecutar la acción. Para obtener más información sobre la respuesta en vivo, consulte [Investigación de entidades en dispositivos que usan la respuesta en vivo](live-response.md).
> - El aislamiento completo está disponible para los dispositivos que ejecutan Windows 11, Windows 10, versión 1703 o posterior, Windows Server 2022, Windows Server 2019 y Windows Server 2016.
> - El aislamiento selectivo está disponible para los dispositivos que ejecutan Windows 10, versión 1709 o posterior y Windows 11.
> - Al aislar un dispositivo, solo se permiten determinados procesos y destinos. Por lo tanto, los dispositivos que están detrás de un túnel VPN completo no podrán acceder al servicio en la nube Microsoft Defender para punto de conexión después de que el dispositivo esté aislado. Se recomienda usar una VPN de túnel dividido para Microsoft Defender para punto de conexión y Microsoft Defender tráfico relacionado con la protección basada en la nube de Antivirus.

Esta característica de aislamiento de dispositivo desconecta el dispositivo en peligro de la red mientras conserva la conectividad con el servicio Defender para punto de conexión, que sigue supervisando el dispositivo.

En Windows 10, versión 1709 o posterior, tendrá más control sobre el nivel de aislamiento de red. También puede optar por habilitar Outlook, Microsoft Teams y Skype Empresarial conectividad (por ejemplo, "Aislamiento selectivo").

> [!NOTE]
> Podrá volver a conectar el dispositivo a la red en cualquier momento. El botón de la página del dispositivo cambiará para decir **Liberar del aislamiento** y, a continuación, realizará los mismos pasos que el aislamiento del dispositivo.

Una vez que haya seleccionado **Aislar dispositivo** en la página del dispositivo, escriba un comentario y seleccione **Confirmar**. El Centro de acciones mostrará la información del examen y la escala de tiempo del dispositivo incluirá un nuevo evento.

:::image type="content" source="images/isolate-device.png" alt-text="Página de detalles de un dispositivo aislado" lightbox="images/isolate-device.png":::

> [!NOTE]
> El dispositivo permanecerá conectado al servicio Defender para punto de conexión incluso si está aislado de la red. Si ha elegido habilitar Outlook y Skype Empresarial comunicación, podrá comunicarse con el usuario mientras el dispositivo está aislado.

### <a name="notification-on-device-user"></a>Notificación al usuario del dispositivo

Cuando se aísla un dispositivo, se muestra la siguiente notificación para informar al usuario de que el dispositivo se está aislando de la red:

:::image type="content" source="images/atp-notification-isolate.png" alt-text="Un mensaje sin conexión de red" lightbox="images/atp-notification-isolate.png":::

## <a name="contain-devices-from-the-network"></a>Contener dispositivos de la red
 
> [!NOTE]
> Las funcionalidades de contenido están actualmente en versión preliminar pública. Para obtener información sobre las nuevas características de la versión preliminar de Microsoft 365 Defender y estar entre las primeras en probar las próximas características activando la experiencia de vista previa, consulte [Características de vista previa en Micrsoft 365 Defender](../defender/preview.md).

Cuando haya identificado un dispositivo no administrado que está en peligro o potencialmente en peligro, es posible que desee contener ese dispositivo de la red. Cuando contenga un dispositivo, cualquier Microsoft Defender para punto de conexión dispositivo incorporado bloqueará la comunicación entrante y saliente con ese dispositivo. Esta acción puede ayudar a evitar que los dispositivos vecinos se pongan en peligro mientras el analista de operaciones de seguridad localiza, identifica y corrige la amenaza en el dispositivo en peligro.

> [!NOTE]
> El bloqueo de la comunicación entrante y saliente con un dispositivo "contenido" es compatible con dispositivos incorporados Microsoft Defender para punto de conexión Windows 10 y Windows Server 2019+.

### <a name="how-to-contain-a-device"></a>Cómo contener un dispositivo
 
1. Vaya a la página **Inventario de** dispositivos y seleccione el dispositivo que va a contener.

2. Seleccione **Contener dispositivo** en el menú acciones del control flotante del dispositivo.

:::image type="content" alt-text="Captura de pantalla del mensaje emergente de contenido del dispositivo." source="../../media/defender-endpoint/contain_device.png" lightbox="../../media/defender-endpoint/contain_device.png":::

3. En el elemento emergente Contener dispositivo, escriba un comentario y seleccione **Confirmar**.

:::image type="content" alt-text="Captura de pantalla del elemento de menú Contener dispositivo." source="../../media/defender-endpoint/contain_device_popup.png" lightbox="../../media/defender-endpoint/contain_device_popup.png":::

### <a name="contain-a-device-from-the-device-page"></a>Contener un dispositivo de la página del dispositivo

Un dispositivo también se puede incluir en la página del dispositivo seleccionando **Contener dispositivo** en la barra de acciones:

:::image type="content" alt-text="Captura de pantalla del elemento de menú Contener dispositivo en la página del dispositivo." source="../../media/defender-endpoint/contain_device_page.png" lightbox="../../media/defender-endpoint/contain_device_page.png":::

> [!NOTE]
> Los detalles sobre un dispositivo recién contenido pueden tardar hasta 5 minutos en llegar a Microsoft Defender para punto de conexión dispositivos incorporados.

> [!IMPORTANT]
> - Si un dispositivo contenido cambia su dirección IP, todos los Microsoft Defender para punto de conexión dispositivos incorporados lo reconocerán y comenzarán a bloquear las comunicaciones con la nueva dirección IP. La dirección IP original ya no se bloqueará (puede tardar hasta 5 minutos en ver estos cambios).  
> - En los casos en los que otro dispositivo de la red usa la dirección IP del dispositivo contenido, habrá una advertencia mientras contiene el dispositivo, con un vínculo a la búsqueda avanzada (con una consulta rellenada previamente). Esto proporcionará visibilidad a los demás dispositivos que usan la misma dirección IP para ayudarle a tomar una decisión consciente si desea continuar con la contención del dispositivo.
> - En los casos en los que el dispositivo contenido sea un dispositivo de red, aparecerá una advertencia con un mensaje que indica que esto puede provocar problemas de conectividad de red (por ejemplo, que contiene un enrutador que actúa como puerta de enlace predeterminada). En este momento, podrá elegir si desea contener el dispositivo o no.

Después de contener un dispositivo, si el comportamiento no es el esperado, compruebe que el servicio Motor de filtrado base (BFE) está habilitado en los dispositivos incorporados de Defender para punto de conexión.

### <a name="stop-containing-a-device"></a>Dejar de contener un dispositivo

Podrá dejar de contener un dispositivo en cualquier momento.

1. Seleccione el dispositivo en inventario **de** dispositivos o abra la página del dispositivo.

2. Seleccione **Liberar desde la contención** en el menú de acción. Esta acción restaurará la conexión de este dispositivo a la red.

## <a name="consult-a-threat-expert"></a>Consultar a un experto en amenazas

Puede consultar a un experto en amenazas de Microsoft para obtener más información sobre un dispositivo potencialmente comprometido o ya comprometido. Expertos en amenazas de Microsoft se pueden contratar directamente desde el Microsoft 365 Defender para obtener una respuesta oportuna y precisa. Los expertos proporcionan información no solo sobre un dispositivo potencialmente comprometido, sino también para comprender mejor las amenazas complejas, las notificaciones de ataque dirigidas que recibe, o si necesita más información sobre las alertas o un contexto de inteligencia sobre amenazas que ve en el panel del portal.

Consulte [Consulta con un experto en amenazas de Microsoft](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) para obtener más información.

## <a name="check-activity-details-in-action-center"></a>Comprobar los detalles de actividad en el Centro de actividades

El **Centro de acciones** proporciona información sobre las acciones que se realizaron en un dispositivo o archivo. Podrá ver los detalles siguientes:

- Colección de paquetes de investigación
- Examen antivirus
- Restricción de la aplicación
- Aislamiento del dispositivo

También se muestran todos los demás detalles relacionados, por ejemplo, la fecha y hora de envío, el usuario que envía y si la acción se realizó correctamente o no.

:::image type="content" source="images/action-center-details.png" alt-text="Centro de acciones con información" lightbox="images/action-center-details.png":::


## <a name="see-also"></a>Vea también

- [Realizar acciones de respuesta en un archivo](respond-file-alerts.md)
- [Acciones de respuesta manual en Microsoft Defender para punto de conexión Plan 1](defender-endpoint-plan-1.md#manual-response-actions)
- [Imprecisión del informe](/microsoft-365/security/defender-endpoint/tvm-security-recommendation#report-inaccuracy)
