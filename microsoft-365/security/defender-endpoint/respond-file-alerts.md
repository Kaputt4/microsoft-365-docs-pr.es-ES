---
title: Realizar acciones de respuesta en un archivo de Microsoft Defender para endpoint
description: Lleve a cabo acciones de respuesta en alertas relacionadas con archivos al detener y anular un archivo o bloquear un archivo y comprobar los detalles de la actividad.
keywords: responder, detener y poner en cuarentena, bloquear archivo, análisis profundo
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
ms.openlocfilehash: 388d71ce4606acabaafdb32ba1baff87286951f1
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998793"
---
# <a name="take-response-actions-on-a-file"></a>Realizar acciones de respuesta en un archivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-responddile-abovefoldlink)

Responda rápidamente a los ataques detectados deteniendo y anulando archivos o bloqueando un archivo. Después de realizar acciones en los archivos, puede comprobar los detalles de la actividad en el Centro de acciones.

Las acciones de respuesta están disponibles en la página de perfil detallada de un archivo. Una vez en esta página, puede cambiar entre los diseños de página nuevo y antiguo cambiando la **nueva página archivo**. El resto de este artículo describe el diseño de página más reciente.

Las acciones de respuesta se ejecutan en la parte superior de la página de archivos e incluyen:

- Detener y poner en cuarentena el archivo
- Agregar indicador
- Descargar archivo
- Consultar a un experto en amenazas
- Centro de actividades

También puede enviar archivos para un análisis profundo, para ejecutar el archivo en un espacio aislado seguro en la nube. Cuando se complete el análisis, se obtiene un informe detallado que proporciona información sobre el comportamiento del archivo. Puede enviar archivos para análisis profundo y leer informes anteriores seleccionando la **pestaña Análisis profundo.** Se encuentra debajo de las tarjetas de información de archivos.

Algunas acciones requieren ciertos permisos. En la tabla siguiente se describe qué acción pueden realizar ciertos permisos en archivos ejecutables portátiles (PE) y que no son PE:

| Permiso             | Archivos PE | Archivos que no son PE |
| :--------------------- | :------: | :----------: |
| Ver datos              |     X    |       X      |
| Investigación de alertas   | &#x2611; |       X      |
| Respuesta en directo básica    |     X    |       X      |
| Respuesta en directo avanzada | &#x2611; |   &#x2611;   |

Para obtener más información sobre los roles, vea [Create and manage roles for role-based access control](user-roles.md).

## <a name="stop-and-quarantine-files-in-your-network"></a>Detener y poner en cuarentena archivos de la red

Puede contener un ataque en su organización al detener el proceso malintencionado y anular el archivo donde se observó.

> [!IMPORTANT]
> Solo puede realizar esta acción si:
>
> - El dispositivo en el que estás llevando a Windows 10, versión 1703 o posterior
> - El archivo no pertenece a editores de terceros de confianza o no está firmado por Microsoft
> - Antivirus de Microsoft Defender debe ejecutarse al menos en modo pasivo. Para obtener más información, [vea Antivirus de Microsoft Defender compatibilidad](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).

La **acción Detener y poner en** cuarentena archivo incluye la detención de procesos en ejecución, la cuarentena de los archivos y la eliminación de datos persistentes, como las claves del Registro.

Esta acción tiene efecto en dispositivos con Windows 10, versión 1703 o posterior, donde se observó el archivo en los últimos 30 días.

> [!NOTE]
> Podrás restaurar el archivo desde la cuarentena en cualquier momento.

### <a name="stop-and-quarantine-files"></a>Detener y poner en cuarentena los archivos

1. Seleccione el archivo que desea detener y poner en cuarentena. Puede seleccionar un archivo de cualquiera de las siguientes vistas o usar el cuadro De búsqueda:

   - **Alertas:** haga clic en los vínculos correspondientes de la línea de tiempo Descripción o Detalles de la escala de tiempo del artículo de alerta
   - **Cuadro de búsqueda:** **seleccione Archivo** en el menú desplegable y escriba el nombre del archivo

   > [!NOTE]
   > La acción de detener y poner en cuarentena el archivo está limitada a un máximo de 1000 dispositivos. Para detener un archivo en un mayor número de dispositivos, vea [Agregar indicador para bloquear o permitir el archivo](#add-indicator-to-block-or-allow-a-file).

2. Vaya a la barra superior y seleccione **Detener y Poner en cuarentena archivo**.

   ![Imagen de la acción detener y poner en cuarentena el archivo](images/atp-stop-quarantine-file.png)

3. Especifique un motivo y, a continuación, **seleccione Confirmar**.

   ![Imagen de la ventana modal del archivo de detenerse y poner en cuarentena](images/atp-stop-quarantine.png)

   El Centro de acciones muestra la información de envío:
   
   ![Imagen del centro de acciones de archivos de detenerse y poner en cuarentena](images/atp-stopnquarantine-file.png)

   - **Tiempo de envío:** muestra cuándo se envió la acción.
   - **Correcto:** muestra el número de dispositivos en los que se ha detenido y puesto en cuarentena el archivo.
   - **Error:** muestra el número de dispositivos en los que se ha fallado la acción y los detalles sobre el error.
   - **Pendiente:** muestra el número de dispositivos desde los que aún se ha detenido y puesto en cuarentena el archivo. Esto puede tardar tiempo en casos en los que el dispositivo está desconectado o no conectado a la red.

4. Seleccione cualquiera de los indicadores de estado para ver más información sobre la acción. Por ejemplo, seleccione **Error** al ver dónde falló la acción.

**Notificación en el usuario del dispositivo:**</br>
Cuando se quita el archivo de un dispositivo, se muestra la siguiente notificación:

![Imagen de notificación en el usuario del dispositivo](images/atp-notification-file.png)

En la escala de tiempo del dispositivo, se agrega un nuevo evento para cada dispositivo en el que se detuvo y se pone en cuarentena un archivo.

Se muestra una advertencia antes de implementar la acción para los archivos que se usan ampliamente en toda la organización. Es para validar que la operación está diseñada.

## <a name="restore-file-from-quarantine"></a>Restaurar archivo de la cuarentena

Puede revertir y quitar un archivo de la cuarentena si ha determinado que está limpio después de una investigación. Ejecute el siguiente comando en cada dispositivo en el que se ha puesto en cuarentena el archivo.

1. Abra un símbolo del sistema con privilegios elevados en el dispositivo:

   1. Vaya a **Inicio** y escriba _cmd_.

   1. Haga clic con el **botón secundario en Símbolo del sistema** y seleccione Ejecutar como **administrador.**

2. Escriba el siguiente comando y presione **Entrar**:

   ```console
   “%ProgramFiles%\Windows Defender\MpCmdRun.exe” –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
   ```

   > [!NOTE]
   > En algunos escenarios, **ThreatName** puede aparecer como: EUS:Win32/CustomEnterpriseBlock!cl.
   >
   > Defender for Endpoint restaurará todos los archivos bloqueados personalizados que se han puesto en cuarentena en este dispositivo en los últimos 30 días.

> [!IMPORTANT]
> Es posible que un archivo que se haya puesto en cuarentena como una amenaza de red potencial no pueda recuperarse. Si un usuario intenta restaurar el archivo después de la cuarentena, es posible que ese archivo no sea accesible. Esto puede deberse a que el sistema ya no tiene credenciales de red para tener acceso al archivo. Normalmente, esto es el resultado de un inicio de sesión temporal en un sistema o carpeta compartida y los tokens de acceso expiraron.

## <a name="download-or-collect-file"></a>Descargar o copiar archivos

Si selecciona **Descargar archivo de** las acciones de respuesta, puede descargar un archivo local protegido con contraseña .zip que contenga el archivo. Aparecerá un flyout donde puede registrar un motivo para descargar el archivo y establecer una contraseña.

De forma predeterminada, no podrá descargar archivos que estén en cuarentena.

![Imagen de la acción de archivo de descarga](images/atp-download-file-action.png)

### <a name="collect-files"></a>Recopilar archivos

Si Microsoft Defender para endpoint no ha almacenado un archivo, no puede descargarlo. En su lugar, verá un botón **Recopilar** archivo en la misma ubicación. Si no se ha visto un archivo en la organización en los últimos 30 días, se deshabilitará **Recopilar** archivo.
> [!Important]
> Es posible que un archivo que se haya puesto en cuarentena como una amenaza de red potencial no pueda recuperarse. Si un usuario intenta restaurar el archivo después de la cuarentena, es posible que ese archivo no sea accesible. Esto puede deberse a que el sistema ya no tiene credenciales de red para tener acceso al archivo. Normalmente, esto es el resultado de un inicio de sesión temporal en un sistema o carpeta compartida y los tokens de acceso expiraron.

## <a name="add-indicator-to-block-or-allow-a-file"></a>Agregar indicador para bloquear o permitir un archivo

Impedir la propagación posterior de un ataque en la organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso. Si conoce un archivo ejecutable portátil (PE) potencialmente malintencionado, puede bloquearlo. Esta operación evitará que se lea, se escriba o se ejecute en dispositivos de la organización.

> [!IMPORTANT]
>
> - Esta característica está disponible si su organización usa Antivirus de Microsoft Defender y la protección entregada en la nube está habilitada. Para obtener más información, vea [Manage cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
>
> - La versión del cliente Antimalware debe ser 4.18.1901.x o posterior.
> - Esta característica está diseñada para evitar que el malware sospechoso (o los archivos potencialmente malintencionados) se descarguen de la web. Actualmente es compatible con archivos ejecutables portátiles (PE), incluidos _.exe_ archivos _.dll_ archivos. La cobertura se extenderá con el tiempo.
> - Esta acción de respuesta está disponible para dispositivos Windows 10 versión 1703 o posterior.
> - La función permitir o bloquear no se puede realizar en archivos si la clasificación del archivo existe en la memoria caché del dispositivo antes de la acción permitir o bloquear.

> [!NOTE]
> El archivo PE debe estar en la escala de tiempo del dispositivo para poder realizar esta acción.
>
> Puede haber un par de minutos de latencia entre el momento en que se hace la acción y el archivo real que se está bloqueando.

### <a name="enable-the-block-file-feature"></a>Habilitar la característica de archivo de bloqueo

Para empezar a bloquear archivos, primero debe activar la característica [ **Bloquear**](advanced-features.md) o permitir en Configuración.
### <a name="allow-or-block-file"></a>Permitir o bloquear archivo

Cuando agregas un hash de indicador para un archivo, puedes elegir generar una alerta y bloquear el archivo siempre que un dispositivo de la organización intente ejecutarlo.

Los archivos bloqueados automáticamente por un indicador no aparecerán en el Centro de acciones del archivo, pero las alertas seguirán estando visibles en la cola de alertas.

Consulta [Administrar indicadores para](manage-indicators.md) obtener más información sobre cómo bloquear y generar alertas en los archivos.

Para detener el bloqueo de un archivo, quite el indicador. Puede hacerlo a través de la acción **Editar indicador** en la página de perfil del archivo. Esta acción estará visible en la  misma posición que la acción Agregar indicador, antes de agregar el indicador.

También puede editar indicadores desde la **página Configuración,** en   >  **Indicadores de reglas**. Los indicadores se enumeran en esta área mediante el hash de su archivo.

## <a name="consult-a-threat-expert"></a>Consultar a un experto en amenazas

Consulta a un experto en amenazas de Microsoft para obtener más información sobre un dispositivo potencialmente en peligro o dispositivos que ya están en peligro. Expertos en amenazas de Microsoft se contratan directamente desde dentro del Centro de seguridad de Microsoft Defender para una respuesta rápida y precisa. Los expertos proporcionan información sobre un dispositivo potencialmente comprometido y te ayudan a comprender las amenazas complejas y las notificaciones de ataque dirigidas. También pueden proporcionar información sobre las alertas o un contexto de inteligencia de amenazas que se ve en el panel del portal.

Consulte [Consulte a un experto en amenazas de Microsoft](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) para obtener más información.

## <a name="check-activity-details-in-action-center"></a>Comprobar los detalles de actividad en el Centro de actividades

El **Centro de acciones** proporciona información sobre las acciones realizadas en un dispositivo o archivo. Puede ver los siguientes detalles:

- Colección de paquetes de investigación
- Examen antivirus
- Restricción de aplicaciones
- Aislamiento de dispositivos

También se muestran todos los demás detalles relacionados, como la fecha y hora del envío, el envío de usuario y si la acción se ha hecho correctamente o se ha fallado.

![Imagen del centro de acción con información](images/action-center-details.png)

## <a name="deep-analysis"></a>Análisis detallado

Las investigaciones de seguridad cibernética suelen desencadenarse mediante una alerta. Las alertas están relacionadas con uno o varios archivos observados que a menudo son nuevos o desconocidos. La selección de un archivo le lleva a la vista de archivos donde puede ver los metadatos del archivo. Para enriquecer los datos relacionados con el archivo, puede enviar el archivo para un análisis profundo.

La característica análisis profundo ejecuta un archivo en un entorno de nube seguro y totalmente instrumentado. Los resultados de análisis profundo muestran las actividades del archivo, los comportamientos observados y los artefactos asociados, como archivos eliminados, modificaciones del Registro y comunicación con ip.
Actualmente, el análisis profundo admite un amplio análisis de archivos ejecutables portátiles (PE) (incluidos _.exe_ archivos _.dll_ portátil).

El análisis profundo de un archivo tarda varios minutos. Una vez completado el análisis de archivos, la pestaña Análisis profundo se actualizará para mostrar un resumen y la fecha y hora de los últimos resultados disponibles.

El resumen de análisis profundo incluye una lista de *comportamientos observados,* algunos de los cuales pueden indicar actividad malintencionada y *observables,* incluidos los ip contactados y los archivos creados en el disco. Si no se encontró nada, estas secciones mostrarán un breve mensaje.

Los resultados del análisis profundo se comparan con la inteligencia de amenazas y cualquier coincidencia generará alertas adecuadas.

Use la característica de análisis profundo para investigar los detalles de cualquier archivo, normalmente durante una investigación de una alerta o por cualquier otro motivo en el que sospeche un comportamiento malintencionado. Esta característica está disponible en la **pestaña Análisis profundo,** en la página de perfil del archivo.<br/>
<br/>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4aAYy?rel=0]

**Enviar** para análisis profundo está habilitado cuando el archivo está disponible en la colección de muestras back-end de Defender for Endpoint, o si se observó en un dispositivo Windows 10 que admite el envío a un análisis profundo.

> [!NOTE]
> Solo los archivos Windows 10 pueden recopilarse automáticamente.

También puedes enviar un ejemplo a través del Portal del Centro de seguridad de [Microsoft](https://www.microsoft.com/security/portal/submission/submit.aspx) si  el archivo no se observó en un dispositivo Windows 10 y esperar a que el botón Enviar para análisis profundo esté disponible.

> [!NOTE]
> Debido a los flujos de procesamiento back-end en el Portal del Centro de seguridad de Microsoft, podría haber hasta 10 minutos de latencia entre el envío de archivos y la disponibilidad de la característica de análisis profundo en Defender para endpoint.

### <a name="submit-files-for-deep-analysis"></a>Enviar archivos para análisis profundo

1. Seleccione el archivo que desea enviar para un análisis profundo. Puede seleccionar o buscar un archivo en cualquiera de las vistas siguientes:

    - **Alertas:** seleccione los vínculos de archivo de **la línea de tiempo Descripción** o **Detalles** de la línea de tiempo de artículo de alerta
    - **Lista dispositivos:** seleccione los vínculos de archivo de la **sección Descripción** o **Detalles** de la sección Dispositivo **en la** organización
    - **Cuadro de búsqueda:** **seleccione Archivo** en el menú desplegable y escriba el nombre del archivo

2. En la **pestaña Análisis profundo** de la vista archivo, seleccione **Enviar**.

   ![Solo puede enviar archivos PE en la sección de detalles del archivo](images/submit-file.png)

   > [!NOTE]
   > Solo se admiten archivos PE, incluidos _.exe_ y _.dll_ archivos.

   Se muestra una barra de progreso y proporciona información sobre las distintas etapas del análisis. A continuación, puede ver el informe cuando se haya realizado el análisis.

> [!NOTE]
> Según la disponibilidad del dispositivo, el tiempo de recolección de muestras puede variar. Hay un tiempo de espera de 3 horas para la colección de muestras. La colección producirá un error y la operación se anulará si no hay informes de dispositivos Windows 10 en línea en ese momento. Puede volver a enviar archivos para un análisis profundo para obtener datos nuevos en el archivo.

### <a name="view-deep-analysis-reports"></a>Ver informes de análisis profundo

Vea el informe de análisis profundo proporcionado para ver información más detallada sobre el archivo enviado. Esta característica está disponible en el contexto de vista de archivos.

Puede ver el informe completo que proporciona detalles en las secciones siguientes:

- Behaviors
- Observables

Los detalles proporcionados pueden ayudarle a investigar si hay indicaciones de un posible ataque.

1. Seleccione el archivo que envió para un análisis profundo.
2. Seleccione la **pestaña Análisis profundo.** Si hay informes anteriores, el resumen del informe aparecerá en esta pestaña.

    ![El informe de análisis profundo muestra información detallada en varias categorías](images/analysis-results-nothing500.png)

#### <a name="troubleshoot-deep-analysis"></a>Solucionar problemas de análisis profundo

Si encuentra un problema al intentar enviar un archivo, pruebe cada uno de los siguientes pasos de solución de problemas.

1. Asegúrese de que el archivo en cuestión es un archivo PE. Los archivos PE suelen _tener.exe_ _o.dll_ (aplicaciones o programas ejecutables).

2. Asegúrese de que el servicio tiene acceso al archivo, que todavía existe y que no se ha dañado ni modificado.

3. Espere un poco e intente enviar el archivo de nuevo. La cola puede estar llena o hubo un error de comunicación o conexión temporal.

4. Si la directiva de colección de ejemplo no está configurada, el comportamiento predeterminado es permitir la colección de muestras. Si está configurado, compruebe que la configuración de directiva permite la colección de muestras antes de enviar el archivo de nuevo. Cuando se configura la colección de ejemplo, compruebe el siguiente valor del Registro:

    ```console
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 – block sample collection
      Value = 1 – allow sample collection
    ```

1. Cambie la unidad organizativa a través de la directiva de grupo. Para obtener más información, vea [Configure with Group Policy](configure-endpoints-gp.md).

1. Si estos pasos no resuelven el problema, póngase en [contacto winatp@microsoft.com](mailto:winatp@microsoft.com).

## <a name="related-topics"></a>Temas relacionados

- [Realizar acciones de respuesta en un dispositivo](respond-machine-alerts.md)
- [Investigar archivos](investigate-files.md)
