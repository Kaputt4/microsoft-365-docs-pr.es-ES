---
title: Realizar acciones de respuesta en un dispositivo en Microsoft Defender para endpoint
description: Realiza acciones de respuesta en un dispositivo como aislar dispositivos, recopilar un paquete de investigación, administrar etiquetas, ejecutar análisis antivirus y restringir la ejecución de aplicaciones.
keywords: responder, aislar, aislar el dispositivo, recopilar paquete de investigación, centro de acción, restringir, administrar etiquetas, av scan, restringir la aplicación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ae8b08ce3d5bcc34e91f031223108fca053348ce
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572398"
---
# <a name="take-response-actions-on-a-device"></a>Realizar acciones de respuesta en un dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-respondmachine-abovefoldlink) 

Responda rápidamente a los ataques detectados aislando dispositivos o recopilando un paquete de investigación. Después de realizar acciones en dispositivos, puedes comprobar los detalles de la actividad en el Centro de acciones.

Las acciones de respuesta se ejecutan en la parte superior de una página de dispositivo específica e incluyen:

- Administrar etiquetas
- Iniciar investigación automatizada
- Iniciar sesión de respuesta activa
- Recopilar paquete de investigación
- Ejecutar examen antivirus
- Restringir ejecución de aplicación
- Aislar dispositivo
- Consultar a un experto en amenazas
- Centro de actividades

[![Imagen de las acciones de respuesta ](images/response-actions.png)](images/response-actions.png#lightbox)

 Puedes encontrar páginas de dispositivo en cualquiera de las siguientes vistas:

- **Panel de operaciones de seguridad:** seleccione un nombre de dispositivo en la tarjeta Dispositivos en riesgo.
- **Cola de alertas:** seleccione el nombre del dispositivo junto al icono del dispositivo en la cola de alertas.
- **Lista de dispositivos:** seleccione el título del nombre del dispositivo de la lista de dispositivos.
- **Cuadro de búsqueda:** seleccione Dispositivo en el menú desplegable y escriba el nombre del dispositivo.

>[!IMPORTANT]
> - Estas acciones de respuesta solo están disponibles para dispositivos Windows 10 versión 1703 o posterior. 
> - Para las plataformas Windows, las capacidades de respuesta (como el aislamiento de dispositivos) dependen de las capacidades de terceros.

## <a name="manage-tags"></a>Administrar etiquetas

Agregar o administrar etiquetas para crear una afiliación de grupo lógico. Las etiquetas de dispositivo admiten la asignación adecuada de la red, lo que te permite adjuntar diferentes etiquetas para capturar el contexto y habilitar la creación de listas dinámicas como parte de un incidente.

Para obtener más información sobre el etiquetado de dispositivos, consulta [Crear y administrar etiquetas de dispositivo.](machine-tags.md)

## <a name="initiate-automated-investigation"></a>Iniciar investigación automatizada

Puedes iniciar una nueva investigación automatizada de propósito general en el dispositivo si es necesario. Mientras se ejecuta una investigación, cualquier otra alerta generada desde el dispositivo se agregará a una investigación automatizada en curso hasta que se complete esa investigación. Además, si se ve la misma amenaza en otros dispositivos, estos dispositivos se agregan a la investigación.

Para obtener más información sobre las investigaciones automatizadas, vea [Overview of Automated investigations](automated-investigations.md).

## <a name="initiate-live-response-session"></a>Iniciar sesión de respuesta activa

La respuesta en directo es una funcionalidad que te proporciona acceso instantáneo a un dispositivo mediante una conexión remota del shell. Esto le da la capacidad de realizar un trabajo de investigación en profundidad y tomar acciones de respuesta inmediatas para contener rápidamente las amenazas identificadas, en tiempo real.

La respuesta en directo está diseñada para mejorar las investigaciones, ya que permite recopilar datos forenses, ejecutar scripts, enviar entidades sospechosas para su análisis, corregir amenazas y buscar proactivamente amenazas emergentes.

Para obtener más información sobre la respuesta en directo, vea [Investigar entidades en dispositivos con respuesta en directo.](live-response.md)

## <a name="collect-investigation-package-from-devices"></a>Recopilar paquete de investigación de dispositivos

Como parte del proceso de investigación o respuesta, puedes recopilar un paquete de investigación desde un dispositivo. Al recopilar el paquete de investigación, puedes identificar el estado actual del dispositivo y comprender aún más las herramientas y técnicas usadas por el atacante.

Para descargar el paquete (archivo Zip) e investigar los eventos que se produjeron en un dispositivo

1. Selecciona **Recopilar paquete de investigación** en la fila de acciones de respuesta en la parte superior de la página del dispositivo.
2. Especifique en el cuadro de texto por qué desea realizar esta acción. Seleccione **Confirmar**.
3. El archivo zip se descargará

Forma alternativa:

1. Selecciona **Centro de acciones** en la sección acciones de respuesta de la página del dispositivo.

    ![Imagen del botón centro de acción](images/action-center-package-collection.png)

3. En el control desplegable del Centro de acciones, seleccione **Paquete de colección de paquetes disponible** para descargar el archivo zip.
  
    ![Imagen del botón descargar paquete](images/collect-package.png)

El paquete contiene las siguientes carpetas:

| Carpeta | Descripción |
|:---|:---------|
|Autoruns | Contiene un conjunto de archivos que cada uno representa el contenido del registro de un punto de entrada de inicio automático (ASEP) conocido para ayudar a identificar la persistencia del atacante en el dispositivo. </br></br> <div class="alert"><b>NOTA:</b> Si no se encuentra la clave del Registro, el archivo contendrá el siguiente mensaje: "ERROR: el sistema no pudo encontrar la clave o el valor del Registro especificados".</div>                                                                                                                                |
|Programas instalados | Este .CSV contiene la lista de programas instalados que pueden ayudar a identificar lo que está instalado actualmente en el dispositivo. Para obtener más información, [vea Win32_Product clase](https://go.microsoft.com/fwlink/?linkid=841509).                                                                                  |
|Conexiones de red | Esta carpeta contiene un conjunto de puntos de datos relacionados con la información de conectividad que puede ayudar a identificar la conectividad a direcciones URL sospechosas, la infraestructura de comando y control del atacante (C&C), cualquier movimiento lateral o conexiones remotas.</br></br> - ActiveNetConnections.txt: muestra las estadísticas de protocolo y las conexiones de red TCP/IP actuales. Proporciona la capacidad de buscar conectividad sospechosa realizada por un proceso. </br></br> - Arp.txt: muestra las tablas de caché del protocolo de resolución de direcciones (ARP) actuales para todas las interfaces. </br></br> La memoria caché ARP puede revelar hosts adicionales en una red que se han visto comprometidos o sistemas sospechosos en la red que podrían haber sido usados para ejecutar un ataque interno.</br></br> - DnsCache.txt: muestra el contenido de la memoria caché de resolución de cliente DNS, que incluye entradas precargadas desde el archivo hosts locales y los registros de recursos obtenidos recientemente para las consultas de nombre resueltas por el equipo. Esto puede ayudar a identificar conexiones sospechosas. </br></br> - IpConfig.txt: muestra la configuración completa de TCP/IP para todos los adaptadores. Los adaptadores pueden representar interfaces físicas, como adaptadores de red instalados o interfaces lógicas, como conexiones de acceso telefónico. </br></br> - FirewallExecutionLog.txt y pfirewall.log                                                                                  |
| Archivos de prefetch| Windows Los archivos prefetch están diseñados para acelerar el proceso de inicio de la aplicación. Se puede usar para realizar un seguimiento de todos los archivos usados recientemente en el sistema y buscar seguimientos de aplicaciones que podrían haber sido eliminadas, pero que aún se pueden encontrar en la lista de archivos de prefetch. </br></br> - Carpeta Prefetch: contiene una copia de los archivos de prefetch de `%SystemRoot%\Prefetch` . NOTA: Se recomienda descargar un visor de archivos de prefetch para ver los archivos de prefetch. </br></br> - PrefetchFilesList.txt: contiene la lista de todos los archivos copiados que se pueden usar para realizar un seguimiento si hubo algún error de copia en la carpeta de captura previa.                                                                                                      |
| Procesos| Contiene un .CSV que enumera los procesos en ejecución, que proporciona la capacidad de identificar los procesos actuales que se ejecutan en el dispositivo. Esto puede ser útil al identificar un proceso sospechoso y su estado.                                                                                                                                                                                                       |
| Tareas programadas| Contiene un archivo .CSV que enumera las tareas programadas, que se pueden usar para identificar rutinas realizadas automáticamente en un dispositivo elegido para buscar código sospechoso que se estableció para ejecutarse automáticamente.                                                                                                                                                                                                      |
| Registro de eventos de seguridad| Contiene el registro de eventos de seguridad, que contiene registros de actividad de inicio de sesión o cierre de sesión, u otros eventos relacionados con la seguridad especificados por la directiva de auditoría del sistema. </br></br><div class="alert"><b>NOTA:</b> Abra el archivo de registro de eventos con el Visor de eventos.</div>                                                                                    |
| Servicios| Contiene un .CSV que enumera los servicios y sus estados.                                                                                      |
| Windows Sesiones de bloque de mensajes de servidor (SMB) | Enumera el acceso compartido a archivos, impresoras y puertos serie y comunicaciones diversas entre nodos de una red. Esto puede ayudar a identificar la exfiltración de datos o el movimiento lateral. </br></br> Contiene archivos para SMBInboundSessions y SMBOutboundSession. </br></br> <div class="alert"><b>NOTA:</b> Si no hay sesiones (entrantes o salientes), se obtiene un archivo de texto que le dirá que no se han encontrado sesiones SMB.</div>                                                                                                                          |
| Información del sistema| Contiene un SystemInformation.txt que enumera la información del sistema, como la versión del sistema operativo y las tarjetas de red.                                                                                     |
| Directorios temporales| Contiene un conjunto de archivos de texto que enumera los archivos ubicados en %Temp% para todos los usuarios del sistema. </br></br> Esto puede ayudar a realizar un seguimiento de los archivos sospechosos que un atacante puede haber eliminado en el sistema. </br></br> <div class="alert"><b>NOTA:</b> Si el archivo contiene el siguiente mensaje: "El sistema no puede encontrar la ruta de acceso especificada", significa que no hay ningún directorio temporal para este usuario y puede deberse a que el usuario no ha iniciar sesión en el sistema.</div>                                                                                                                                         |
| Usuarios y grupos| Proporciona una lista de archivos que cada uno representa a un grupo y sus miembros.                                                                                                                   |
|WdSupportLogs| Proporciona el MpCmdRunLog.txt y MPSupportFiles.cab  </br></br> <div class="alert"><b>NOTA:</b> Esta carpeta solo se creará en Windows 10, versión 1709 o posterior con el paquete acumulativo de actualizaciones de febrero de 2020 o más reciente instalado:</br> Win10 1709 (RS3) Compilación 16299.1717 : [KB4537816](https://support.microsoft.com/en-us/help/4537816/windows-10-update-kb4537816) </br> Win10 1803 (RS4) Compilación 17134.1345 : [KB4537795](https://support.microsoft.com/en-us/help/4537795/windows-10-update-kb4537795) </br> Win10 1809 (RS5) Compilación 17763.1075 : [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818) </br> Win10 1903/1909 (19h1/19h2) compila 18362.693 y 18363.693 : [KB4535996](https://support.microsoft.com/en-us/help/4535996/windows-10-update-kb4535996) </div>                                                                                                                    |
| CollectionSummaryReport.xls| Este archivo es un resumen de la colección de paquetes de investigación, contiene la lista de puntos de datos, el comando usado para extraer los datos, el estado de ejecución y el código de error en caso de error. Puede usar este informe para realizar un seguimiento de si el paquete incluye todos los datos esperados e identificar si hubo algún error. |

## <a name="run-microsoft-defender-antivirus-scan-on-devices"></a>Ejecutar Antivirus de Microsoft Defender digitalización en dispositivos

Como parte del proceso de investigación o respuesta, puedes iniciar de forma remota un examen antivirus para ayudar a identificar y corregir malware que podría estar presente en un dispositivo en peligro.

>[!IMPORTANT]
>- Esta acción está disponible para dispositivos Windows 10 versión 1709 o posterior.
>- Un Antivirus de Microsoft Defender (Antivirus de Microsoft Defender) puede ejecutarse junto con otras soluciones antivirus, independientemente de si Antivirus de Microsoft Defender es la solución antivirus activa o no. Microsoft Defender AV puede estar en modo pasivo. Para obtener más información, [vea Antivirus de Microsoft Defender compatibilidad](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility.md).

Uno que haya seleccionado **Ejecutar examen antivirus,** seleccione el tipo de examen que desea ejecutar (rápido o completo) y agregue un comentario antes de confirmar el examen.

![Imagen de notificación para seleccionar examen rápido o examen completo y agregar comentario](images/run-antivirus.png)

El Centro de acciones mostrará la información del examen y la escala de tiempo del dispositivo incluirá un nuevo evento, lo que refleja que se envió una acción de examen en el dispositivo. Las alertas antivirus de Microsoft Defender reflejarán las detecciones que se han producido durante el examen.

>[!NOTE]
>Al desencadenar un examen con la acción de respuesta de Defender for Endpoint, el valor "ScanAvgCPULoadFactor" del antivirus de Microsoft Defender sigue aplicando y limitando el impacto de la CPU del examen.<br> Si ScanAvgCPULoadFactor no está configurado, el valor predeterminado es un límite del 50 % de carga máxima de CPU durante un examen.<br>
>Para obtener más información, [vea configure-advanced-scan-types-microsoft-defender-antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-advanced-scan-types-microsoft-defender-antivirus).

## <a name="restrict-app-execution"></a>Restringir ejecución de aplicación

Además de contener un ataque al detener procesos malintencionados, también puedes bloquear un dispositivo e impedir que se ejecuten los intentos posteriores de programas potencialmente malintencionados.

>[!IMPORTANT]
> - Esta acción está disponible para dispositivos Windows 10 versión 1709 o posterior.
> - Esta característica está disponible si su organización usa Antivirus de Microsoft Defender.
> - Esta acción debe cumplir los requisitos de firma y formatos de directiva de integridad de código Windows Defender control de aplicaciones. Para obtener más información, vea [Code integrity policy formats and signing](https://docs.microsoft.com/windows/device-security/device-guard/requirements-and-deployment-planning-guidelines-for-device-guard#code-integrity-policy-formats-and-signing).

Para restringir la ejecución de una aplicación, se aplica una directiva de integridad de código que solo permite que los archivos se ejecuten si están firmados por un certificado emitido por Microsoft. Este método de restricción puede ayudar a evitar que un atacante controle los dispositivos en peligro y realice más actividades malintencionadas.

>[!NOTE]
>Podrás revertir la restricción de que las aplicaciones se ejecuten en cualquier momento. El botón de la página del dispositivo cambiará por decir Quitar **restricciones** de la aplicación y, a continuación, tomarás los mismos pasos que restringir la ejecución de la aplicación.

Una vez que haya seleccionado Restringir la ejecución **de la** aplicación en la página del dispositivo, escriba un comentario y seleccione **Confirmar**. El Centro de acciones mostrará la información del examen y la escala de tiempo del dispositivo incluirá un nuevo evento.

![Imagen de notificación de restricción de aplicaciones](images/restrict-app-execution.png)

**Notificación en el usuario del dispositivo:**</br>
Cuando una aplicación está restringida, se muestra la siguiente notificación para informar al usuario de que una aplicación está siendo restringida para que no se ejecute:

![Imagen de la restricción de la aplicación](images/atp-app-restriction.png)

## <a name="isolate-devices-from-the-network"></a>Aislar dispositivos de la red

Según la gravedad del ataque y la confidencialidad del dispositivo, es posible que quieras aislar el dispositivo de la red. Esta acción puede ayudar a evitar que el atacante controle el dispositivo en peligro y realice otras actividades, como la exfiltración de datos y el movimiento lateral.

>[!IMPORTANT]
>- El aislamiento total está disponible para dispositivos Windows 10, versión 1703.
>- El aislamiento selectivo está disponible para dispositivos Windows 10 versión 1709 o posterior.
>- Al aislar un dispositivo, solo se permiten determinados procesos y destinos. Por lo tanto, los dispositivos que están detrás de un túnel VPN completo no podrán llegar al servicio en la nube de Microsoft Defender para Endpoint después de aislar el dispositivo. Se recomienda usar una VPN de túnel dividido para Microsoft Defender para endpoint y Antivirus de Microsoft Defender tráfico relacionado con la protección basada en la nube.

Esta característica de aislamiento de dispositivos desconecta el dispositivo en peligro de la red y conserva la conectividad con el servicio Defender for Endpoint, que sigue supervisando el dispositivo.

En Windows 10 versión 1709 o posterior, tendrás control adicional sobre el nivel de aislamiento de red. También puede habilitar la conectividad Outlook, Microsoft Teams y Skype Empresarial (a.k.a 'Selective Isolation').

>[!NOTE]
>Podrás volver a conectar el dispositivo a la red en cualquier momento. El botón de la página del dispositivo cambiará a decir **Liberar** del aislamiento y, a continuación, tomarás los mismos pasos que aislar el dispositivo.

Una vez que haya seleccionado **Aislar dispositivo** en la página del dispositivo, escriba un comentario y seleccione **Confirmar**. El Centro de acciones mostrará la información del examen y la escala de tiempo del dispositivo incluirá un nuevo evento.

![Imagen del dispositivo aislado](images/isolate-device.png)

>[!NOTE]
>El dispositivo permanecerá conectado al servicio Defender for Endpoint incluso si está aislado de la red. Si has elegido habilitar la Outlook y Skype Empresarial, podrás comunicarte con el usuario mientras el dispositivo está aislado.

**Notificación en el usuario del dispositivo:**</br>
Cuando se aísla un dispositivo, se muestra la siguiente notificación para informar al usuario de que el dispositivo está aislado de la red:

![Imagen de no conexión de red](images/atp-notification-isolate.png)

## <a name="consult-a-threat-expert"></a>Consultar a un experto en amenazas

Puedes consultar a un experto en amenazas de Microsoft para obtener más información sobre un dispositivo potencialmente en peligro o ya comprometido. Expertos en amenazas de Microsoft puede usarse directamente desde dentro del Centro de seguridad de Microsoft Defender para una respuesta rápida y precisa. Los expertos proporcionan información no solo sobre un dispositivo potencialmente en peligro, sino también para comprender mejor las amenazas complejas, las notificaciones de ataque dirigidas que recibes o si necesitas más información sobre las alertas o un contexto de inteligencia de amenazas que veas en el panel del portal.

Consulte [Consulte a un experto en amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) para obtener más información.


## <a name="check-activity-details-in-action-center"></a>Comprobar los detalles de actividad en el Centro de actividades

El **Centro de acciones** proporciona información sobre las acciones realizadas en un dispositivo o archivo. Podrás ver los siguientes detalles:

- Colección de paquetes de investigación
- Examen antivirus
- Restricción de aplicaciones
- Aislamiento de dispositivos

También se muestran todos los demás detalles relacionados, por ejemplo, fecha y hora de envío, el envío del usuario y si la acción se ha hecho correctamente o se ha fallado.

![Imagen del centro de acción con información](images/action-center-details.png)

## <a name="related-topic"></a>Tema relacionado
- [Realizar acciones de respuesta en un archivo](respond-file-alerts.md)
- [Imprecisión de informe](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation#report-inaccuracy)
