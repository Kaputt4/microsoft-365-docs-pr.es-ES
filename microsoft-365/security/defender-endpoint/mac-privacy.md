---
title: Privacidad para Microsoft Defender para punto de conexión en Mac
description: Controles de privacidad, cómo configurar las opciones de directiva que afectan a la privacidad y a la información sobre los datos de diagnóstico recopilados en Microsoft Defender para punto de conexión en Mac.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, privacidad, diagnóstico
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 96a44fd7bd80d0d348928860be9d97a6d0cc68a6
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68229446"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a>Privacidad para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft se compromete a proporcionarle la información y los controles necesarios para tomar decisiones sobre cómo se recopilan y usan los datos cuando se usa Microsoft Defender para punto de conexión en macOS.

En este tema se describen los controles de privacidad disponibles en el producto, cómo administrar estos controles con la configuración de directiva y más detalles sobre los eventos de datos que se recopilan.

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a>Introducción a los controles de privacidad en Microsoft Defender para punto de conexión en macOS

En esta sección se describen los controles de privacidad de los distintos tipos de datos recopilados por Microsoft Defender para punto de conexión en macOS.

### <a name="diagnostic-data"></a>Datos de diagnóstico

Los datos de diagnóstico se usan para mantener Microsoft Defender para punto de conexión seguros y actualizados, detectar, diagnosticar y corregir problemas, y también realizar mejoras en el producto.

Algunos datos de diagnóstico son necesarios, mientras que otros son opcionales. Le damos la posibilidad de elegir si enviarnos datos de diagnóstico necesarios u opcionales mediante los controles de privacidad, como la configuración de directiva para las organizaciones.

Hay dos niveles de datos de diagnóstico para Microsoft Defender para punto de conexión software cliente entre los que puede elegir:

- **Requerido**: los datos mínimos necesarios para ayudar a mantener Microsoft Defender para punto de conexión seguros, actualizados y con el rendimiento esperado en el dispositivo en el que está instalado.

- **Opcional**: datos adicionales que ayudan a Microsoft a realizar mejoras en el producto y proporcionan información mejorada para ayudar a detectar, diagnosticar y corregir problemas.

De forma predeterminada, solo se envían a Microsoft los datos de diagnóstico necesarios.

### <a name="cloud-delivered-protection-data"></a>Datos de protección entregados en la nube

La protección proporcionada en la nube se usa para proporcionar una protección mayor y más rápida con acceso a los datos de protección más recientes en la nube.

La habilitación del servicio de protección entregada en la nube es opcional, pero es muy recomendable porque proporciona una protección importante contra el malware en los puntos de conexión y en toda la red.

### <a name="sample-data"></a>Datos de ejemplo

Los datos de ejemplo se usan para mejorar las funcionalidades de protección del producto mediante el envío de muestras sospechosas de Microsoft para que se puedan analizar. Habilitar el envío automático de ejemplos es opcional.

Cuando esta característica está habilitada y es probable que el ejemplo recopilado contenga información personal, se solicita al usuario su consentimiento.

## <a name="manage-privacy-controls-with-policy-settings"></a>Administre los controles de privacidad con la configuración de directiva

Si es administrador de TI, es posible que desee configurar estos controles en el nivel empresarial.

Los controles de privacidad de los distintos tipos de datos descritos en la sección anterior se describen en detalle en [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md).

Al igual que con cualquier nueva configuración de directiva, debe probarlas cuidadosamente en un entorno limitado y controlado para asegurarse de que la configuración que configure tenga el efecto deseado antes de implementar la configuración de directiva de forma más amplia en su organización.

## <a name="diagnostic-data-events"></a>Eventos de datos de diagnóstico

En esta sección se describen los datos de diagnóstico necesarios y los que se consideran datos de diagnóstico opcionales, junto con una descripción de los eventos y campos que se recopilan.

### <a name="data-fields-that-are-common-for-all-events"></a>Campos de datos comunes para todos los eventos

Hay cierta información acerca de los eventos que es común a todos, independientemente del subtipo de datos o la categoría.

Los campos siguientes se consideran comunes para todos los eventos:

|Campo|Descripción|
|---|---|
|plataforma|La amplia clasificación de la plataforma en la que se ejecuta la aplicación. Permite a Microsoft identificar en qué plataformas puede producirse un problema para que se pueda priorizar correctamente.|
|machine_guid|Identificador único asociado al dispositivo. Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de instalaciones y cuántos usuarios se ven afectados.|
|sense_guid|Identificador único asociado al dispositivo. Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de instalaciones y cuántos usuarios se ven afectados.|
|org_id|Identificador único asociado a la empresa a la que pertenece el dispositivo. Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de empresas y cuántas empresas se ven afectadas.|
|Host|Nombre del dispositivo local (sin sufijo DNS). Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de instalaciones y cuántos usuarios se ven afectados.|
|product_guid|Identificador único del producto. Permite a Microsoft diferenciar los problemas que afectan a diferentes tipos del producto.|
|app_version|Versión de la Microsoft Defender para punto de conexión en la aplicación macOS. Permite a Microsoft identificar qué versiones del producto muestran un problema para que se pueda priorizar correctamente.|
|sig_version|Versión de la base de datos de inteligencia de seguridad. Permite a Microsoft identificar qué versiones de la inteligencia de seguridad muestran un problema para que se pueda priorizar correctamente.|
|supported_compressions|Lista de algoritmos de compresión admitidos por la aplicación, por ejemplo `['gzip']`. Permite a Microsoft comprender qué tipos de compresión se pueden usar cuando se comunica con la aplicación.|
|release_ring|Anillo al que está asociado el dispositivo (por ejemplo, Insider Fast, Insider Slow, Production). Permite a Microsoft identificar en qué anillo de versión puede producirse un problema para que se pueda priorizar correctamente.|

### <a name="required-diagnostic-data"></a>Datos de diagnósticos necesarios

**Los datos de diagnóstico necesarios** son los datos mínimos necesarios para mantener Microsoft Defender para punto de conexión seguros, actualizados y funcionan según lo esperado en el dispositivo en el que está instalado.

Los datos de diagnóstico necesarios ayudan a identificar problemas con Microsoft Defender para punto de conexión que pueden estar relacionados con una configuración de software o dispositivo. Por ejemplo, puede ayudar a determinar si una característica de Microsoft Defender para punto de conexión se bloquea con más frecuencia en una versión determinada del sistema operativo, con características recién introducidas o cuando algunas características de Microsoft Defender para punto de conexión están deshabilitadas. Los datos de diagnóstico necesarios ayudan a Microsoft a detectar, diagnosticar y corregir estos problemas más rápidamente para reducir el impacto en los usuarios u organizaciones.

#### <a name="software-setup-and-inventory-data-events"></a>Eventos de datos de inventario y configuración de software

**Microsoft Defender para punto de conexión instalación o desinstalación**:

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|correlation_id|Identificador único asociado a la instalación.|
|version|Versión del paquete.|
|severity|Gravedad del mensaje (por ejemplo, informativo).|
|código|Código que describe la operación.|
|text|Información adicional asociada a la instalación del producto.|

**Microsoft Defender para punto de conexión configuración**:

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|antivirus_engine.enable_real_time_protection|Si la protección en tiempo real está habilitada en el dispositivo o no.|
|antivirus_engine.passive_mode|Si el modo pasivo está habilitado en el dispositivo o no.|
|cloud_service.enabled|Si la protección de entrega en la nube está habilitada en el dispositivo o no.|
|cloud_service.timeout|Tiempo de espera cuando la aplicación se comunica con la nube de Microsoft Defender para punto de conexión.|
|cloud_service.heartbeat_interval|Intervalo entre latidos consecutivos enviados por el producto a la nube.|
|cloud_service.service_uri|URI que se usa para comunicarse con la nube.|
|cloud_service.diagnostic_level|Nivel de diagnóstico del dispositivo (obligatorio, opcional).|
|cloud_service.automatic_sample_submission|Si el envío automático de muestras está activado o no.|
|cloud_service.automatic_definition_update_enabled|Si la actualización de definición automática está activada o no.|
|edr.early_preview|Si el dispositivo debe ejecutar características de versión preliminar temprana de EDR.|
|edr.group_id|Identificador de grupo utilizado por el componente de detección y respuesta.|
|edr.tags|Etiquetas definidas por el usuario.|
|Funciones.\[ nombre de característica opcional\]|Lista de características en versión preliminar, junto con si están habilitadas o no.|

#### <a name="product-and-service-usage-data-events"></a>Eventos de datos de uso de productos y servicios

**Informe de actualización de inteligencia de seguridad**:

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|from_version|Versión de inteligencia de seguridad original.|
|to_version|Nueva versión de inteligencia de seguridad.|
|status|Estado de la actualización que indica si se ha realizado correctamente o no.|
|using_proxy|Si la actualización se realizó a través de un proxy.|
|error|Código de error si se produjo un error en la actualización.|
|motivo|Mensaje de error si el archivo actualizado.|

#### <a name="product-and-service-performance-data-events-for-required-diagnostic-data"></a>Eventos de datos de rendimiento de productos y servicios para los datos de diagnóstico necesarios

**Salida inesperada de la aplicación (bloqueo):**

Recopila información del sistema y el estado de una aplicación cuando una aplicación se cierra inesperadamente.

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|v1_crash_count|Número de veces que el proceso del motor V1 se bloquea cada hora en el equipo cliente|
|v2_crash_count|Número de veces que el proceso del motor V2 se bloquea cada hora en el equipo cliente|
|EDR_crash_count|Número de veces que el proceso de EDR se bloquea cada hora en el equipo cliente|

**Estadísticas de extensión de kernel**:

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|version|Versión de Microsoft Defender para punto de conexión en macOS.|
|instance_id|Identificador único generado durante el inicio de la extensión del kernel.|
|trace_level|Nivel de seguimiento de la extensión del kernel.|
|Subsistema|Subsistema subyacente utilizado para la protección en tiempo real.|
|ipc.connect|Número de solicitudes de conexión recibidas por la extensión del kernel.|
|ipc.rejects|Número de solicitudes de conexión rechazadas por la extensión del kernel.|
|ipc.connected|Si hay alguna conexión activa a la extensión del kernel.|

#### <a name="support-data"></a>Datos de soporte técnico

**Registros de diagnóstico**:

Los registros de diagnóstico solo se recopilan con el consentimiento del usuario como parte de la característica de envío de comentarios. Los siguientes archivos se recopilan como parte de los registros de soporte técnico:

- Todos los archivos en */Library/Logs/Microsoft/mdatp/*
- Subconjunto de archivos en */Library/Application Support/Microsoft/Defender/* creados y usados por Microsoft Defender para punto de conexión en macOS
- Subconjunto de archivos en */Library/Managed Preferences* que usa Microsoft Defender para punto de conexión en macOS
- /Library/Logs/Microsoft/autoupdate.log
- $HOME/Library/Preferences/com.microsoft.autoupdate2.plist

### <a name="optional-diagnostic-data"></a>Datos de diagnóstico opcionales

**Los datos de diagnóstico opcionales** son datos adicionales que ayudan a Microsoft a realizar mejoras en el producto y proporcionan información mejorada para ayudar a detectar, diagnosticar y corregir problemas.

Si elige enviarnos sus datos de diagnóstico opcionales, también se incluyen los datos de diagnósticos requeridos.

Entre los ejemplos de datos de diagnóstico opcionales se incluyen los datos que Microsoft recopila sobre la configuración del producto (por ejemplo, el número de exclusiones establecidas en el dispositivo) y el rendimiento del producto (medidas agregadas sobre el rendimiento de los componentes del producto).

#### <a name="software-setup-and-inventory-data-events-for-optional-diagnostic-data"></a>Eventos de datos de inventario y configuración de software para datos de diagnóstico opcionales

**Microsoft Defender para punto de conexión configuración**:

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|connection_retry_timeout|Tiempo de espera de reintento de conexión cuando se comunica con la nube.|
|file_hash_cache_maximum|Tamaño de la memoria caché del producto.|
|crash_upload_daily_limit|Límite de registros de bloqueo cargados diariamente.|
|antivirus_engine.exclusiones[].is_directory|Si la exclusión del examen es un directorio o no.|
|antivirus_engine.exclusiones[].path|Ruta de acceso que se excluyó del examen.|
|antivirus_engine.exclusions[].extension|Extensión excluida del examen.|
|antivirus_engine.exclusions[].name|Nombre del archivo excluido del examen.|
|antivirus_engine.scan_cache_maximum|Tamaño de la memoria caché del producto.|
|antivirus_engine.maximum_scan_threads|Número máximo de subprocesos usados para el examen.|
|antivirus_engine.threat_restoration_exclusion_time|Tiempo de espera antes de que se pueda volver a detectar un archivo restaurado desde la cuarentena.|
|antivirus_engine.threat_type_settings|Configuración de la forma en que el producto controla los distintos tipos de amenazas.|
|filesystem_scanner.full_scan_directory|Directorio de examen completo.|
|filesystem_scanner.quick_scan_directories|Lista de directorios usados en el examen rápido.|
|edr.latency_mode|Modo de latencia usado por el componente de detección y respuesta.|
|edr.proxy_address|Dirección de proxy usada por el componente de detección y respuesta.|

**Configuración de Actualización automática de Microsoft**:

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|how_to_check|Determina cómo se comprueban las actualizaciones del producto (por ejemplo, automáticas o manuales).|
|channel_name|Actualice el canal asociado al dispositivo.|
|manifest_server|Servidor que se usa para descargar actualizaciones.|
|update_cache|Ubicación de la memoria caché usada para almacenar actualizaciones.|

### <a name="product-and-service-usage"></a>Uso de productos y servicios

#### <a name="diagnostic-log-upload-started-report"></a>Informe de inicio de carga del registro de diagnóstico

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|sha256|Identificador SHA256 del registro de soporte técnico.|
|size|Tamaño del registro de soporte técnico.|
|original_path|Ruta de acceso al registro de soporte técnico (siempre en */Library/Application Support/Microsoft/Defender/wdavdiag/*).|
|format|Formato del registro de soporte técnico.|
|Metadatos|Información sobre el contenido del registro de soporte técnico.|

#### <a name="diagnostic-log-upload-completed-report"></a>Informe completado de carga del registro de diagnóstico

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|request_id|Identificador de correlación para la solicitud de carga del registro de soporte técnico.|
|sha256|Identificador SHA256 del registro de soporte técnico.|
|blob_sas_uri|URI usado por la aplicación para cargar el registro de soporte técnico.|

#### <a name="product-and-service-performance-data-events-for-product-and-service-usage"></a>Eventos de datos de rendimiento de productos y servicios para el uso de productos y servicios

**Salida inesperada de la aplicación (bloqueo):**

Cierres de aplicación inesperados y el estado de la aplicación cuando esto ocurre.

**Estadísticas de extensión de kernel**:

Se recopilan los campos siguientes: 

|Campo|Descripción|
|---|---|
|pkt_ack_timeout|Las propiedades siguientes son valores numéricos agregados, que representan el recuento de eventos que se produjeron desde el inicio de la extensión del kernel.|
|pkt_ack_conn_timeout||
|ipc.ack_pkts||
|ipc.nack_pkts||
|ipc.send.ack_no_conn||
|ipc.send.nack_no_conn||
|ipc.send.ack_no_qsq||
|ipc.send.nack_no_qsq||
|ipc.ack.no_space||
|ipc.ack.timeout||
|ipc.ack.ackd_fast||
|ipc.ack.ackd||
|ipc.recv.bad_pkt_len||
|ipc.recv.bad_reply_len||
|ipc.recv.no_waiter||
|ipc.recv.copy_failed||
|ipc.kauth.vnode.mask||
|ipc.kauth.vnode.read||
|ipc.kauth.vnode.write||
|ipc.kauth.vnode.exec||
|ipc.kauth.vnode.del||
|ipc.kauth.vnode.read_attr||
|ipc.kauth.vnode.write_attr||
|ipc.kauth.vnode.read_ex_attr||
|ipc.kauth.vnode.write_ex_attr||
|ipc.kauth.vnode.read_sec||
|ipc.kauth.vnode.write_sec||
|ipc.kauth.vnode.take_own||
|ipc.kauth.vnode.link||
|ipc.kauth.vnode.create||
|ipc.kauth.vnode.move||
|ipc.kauth.vnode.mount||
|ipc.kauth.vnode.denied||
|ipc.kauth.vnode.ackd_before_deadline||
|ipc.kauth.vnode.missed_deadline||
|ipc.kauth.file_op.mask||
|ipc.kauth_file_op.open||
|ipc.kauth.file_op.close||
|ipc.kauth.file_op.close_modified||
|ipc.kauth.file_op.move||
|ipc.kauth.file_op.link||
|ipc.kauth.file_op.exec||
|ipc.kauth.file_op.remove||
|ipc.kauth.file_op.unmount||
|ipc.kauth.file_op.fork||
|ipc.kauth.file_op.create||

## <a name="resources"></a>Recursos

- [Privacidad de Microsoft](https://privacy.microsoft.com/)
